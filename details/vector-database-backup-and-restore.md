## Overview

Vector database backup and restore ensures data durability and recovery from failures. Given the cost of computing embeddings and curating data, robust backup strategies are essential for production systems.

## Backup Strategies

### Full Backups
**Method**: Complete database copy

**Advantages:**
- Simple restore process
- Point-in-time recovery
- Independent backup

**Disadvantages:**
- Large storage requirements
- Long backup time
- Resource intensive

**Frequency**: Daily or weekly

### Incremental Backups
**Method**: Only changes since last backup

**Advantages:**
- Faster backups
- Less storage
- More frequent possible

**Disadvantages:**
- Complex restore (chain required)
- Dependency on previous backups

**Frequency**: Hourly or continuous

### Snapshot-Based
**Method**: Storage-level snapshots

**Advantages:**
- Very fast
- Minimal impact
- Instant restore

**Disadvantages:**
- Requires snapshot support
- Storage overhead

**Supported By**: Cloud-managed services

## Backup Components

### Vector Data
The embeddings themselves:
- Highest priority
- Largest storage requirement
- Can't be easily regenerated (API costs)

### Metadata
Associated attributes:
- Filter fields
- Document IDs
- Custom attributes

### Index Structures
HNSW, IVF, etc.:
- Can be rebuilt from vectors
- Rebuilding is time-consuming
- Consider backing up if large

### Configuration
Database settings:
- Schema definitions
- Index parameters
- Access controls
- Should always backup

## Implementation by Database

### Pinecone
Managed backups:
- Automatic by default
- Point-in-time recovery
- Export collections
```python
# Export to cloud storage
index.backup(
    backup_name="daily_backup",
    destination="s3://bucket/path"
)
```

### Qdrant
Multiple options:
```bash
# Snapshot
curl -X POST 'http://localhost:6333/collections/my_collection/snapshots'

# Full collection
curl 'http://localhost:6333/collections/my_collection' > backup.json
```

### Weaviate
Backup module:
```python
client.backup.create(
    backup_id="backup-1",
    backend="s3",
    include_classes=["Document"]
)
```

### Milvus
Backup utility:
```bash
# Create backup
milvus-backup create -c collection_name

# Restore backup
milvus-backup restore -c collection_name -s backup_id
```

### pgvector (PostgreSQL)
Standard PostgreSQL tools:
```bash
# pg_dump
pg_dump -Fc mydb > backup.dump

# pg_basebackup
pg_basebackup -D /backup/location
```

## Disaster Recovery

### Recovery Time Objective (RTO)
Maximum acceptable downtime:
- Tier 1 (critical): <1 hour
- Tier 2 (important): <4 hours
- Tier 3 (standard): <24 hours

### Recovery Point Objective (RPO)
Maximum acceptable data loss:
- Tier 1: <5 minutes
- Tier 2: <1 hour
- Tier 3: <24 hours

### Strategies by Tier

**Tier 1 (Mission Critical)**
- Continuous replication
- Multiple regions
- Automated failover
- 5-minute incremental backups

**Tier 2 (Production)**
- Hourly backups
- Daily full backups
- Single region with backup region
- Manual failover acceptable

**Tier 3 (Development/Staging)**
- Daily backups
- Single region
- Manual restore
- Longer recovery acceptable

## Backup Best Practices

### 3-2-1 Rule
- **3** copies of data
- **2** different storage types
- **1** offsite/remote backup

### Verification
Test restores regularly:
```python
def verify_backup(backup_path):
    # Restore to test environment
    restore(backup_path, test_db)
    
    # Verify record count
    assert test_db.count() == expected_count
    
    # Sample queries
    results = test_db.search(test_query)
    assert len(results) > 0
    
    # Cleanup
    test_db.delete()
```

### Automation
Scheduled backups:
```yaml
# Cron job
0 2 * * * /backup/scripts/daily_backup.sh
0 */4 * * * /backup/scripts/incremental_backup.sh
```

### Monitoring
Track backup health:
- Last successful backup time
- Backup size trends
- Failure alerts
- Storage usage

### Encryption
Secure backups:
- Encrypt at rest
- Encrypt in transit
- Secure access keys
- Compliance requirements

## Restore Procedures

### Full Restore
1. Provision new database instance
2. Restore from latest full backup
3. Apply incremental backups (if any)
4. Verify data integrity
5. Update application configuration
6. Test functionality
7. Cutover traffic

### Partial Restore
Restore specific collections:
```python
restore_collection(
    collection="documents",
    backup_id="backup-2024-03-22",
    timestamp="2024-03-22T10:00:00Z"
)
```

### Point-in-Time Recovery
Restore to specific moment:
1. Restore latest full backup before target time
2. Apply incremental backups up to target
3. Replay transaction logs if available

## Storage Considerations

### Costs
Example (1M vectors, 768-dim):
- Vector data: ~3 GB
- Daily backups × 30 days: 90 GB
- Monthly cost (S3): ~$2/month

### Retention Policies
Typical schedule:
- Hourly: Keep 24 hours
- Daily: Keep 30 days
- Weekly: Keep 12 weeks
- Monthly: Keep 12 months

### Compression
Reduce storage:
- gzip: 3-10x compression
- Application on-the-fly
- Trade CPU for storage

## Common Failure Scenarios

### Data Corruption
- Restore from last known good backup
- Verify checksums
- Investigate root cause

### Accidental Deletion
- Point-in-time restore
- Restore to temp database
- Export deleted data
- Re-import to production

### Regional Outage
- Failover to backup region
- Restore from cross-region backup
- Update DNS/endpoints

### Security Breach
- Restore from pre-breach backup
- Audit for compromised data
- Rotate credentials
- Security investigation

## Pricing

Backup storage costs vary by provider and strategy; typically $0.02-0.10/GB/month.