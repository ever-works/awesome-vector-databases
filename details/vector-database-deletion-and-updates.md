## Overview

Managing deletions and updates in vector databases requires understanding trade-offs between immediate consistency, performance, and index quality.

## Deletion Strategies

### Hard Delete
```python
# Immediate removal
collection.delete(expr="id in [1, 2, 3]")
```
- Immediate effect
- Can degrade index
- Expensive operation

### Soft Delete
```python
# Mark as deleted
collection.update(id=1, deleted=True)

# Filter in queries
results = collection.search(
    filter="deleted == False"
)
```
- Fast
- Reversible
- Requires filtering
- Takes up space

### Batch Deletion
```python
# Collect IDs to delete
to_delete = [1, 2, 3, ...]

# Delete in batch
if len(to_delete) > 1000:
    collection.delete(expr=f"id in {to_delete}")
```
- More efficient
- Less index disruption

## Update Strategies

### Delete + Insert
```python
# Update is delete + insert
collection.delete(expr="id == 123")
collection.insert(new_data)
```
- Most common
- Guaranteed consistency
- Two operations

### Versioning
```json
{
  "id": "doc_v2",
  "vector": [...],
  "version": 2,
  "previous_version": "doc_v1"
}
```
- Keep history
- Audit trail
- More storage

### Incremental Updates
```python
# Update metadata only (no vector change)
collection.update(
    id=123,
    payload={"status": "published"}
)
```
- Fast
- No re-embedding needed

## Compaction

```python
# Clean up deleted vectors
collection.compact()
```
- Reclaim space
- Improve performance
- Resource intensive

## GDPR/Compliance

### Right to be Forgotten
1. Identify all user vectors
2. Delete from vector DB
3. Delete from document store
4. Purge from backups
5. Audit log the deletion

### Data Retention
```python
# Auto-delete old vectors
delete_before = datetime.now() - timedelta(days=90)
collection.delete(expr=f"timestamp < {delete_before}")
```

## Best Practices

1. **Batch Operations**: Group deletes/updates
2. **Soft Deletes for UX**: Reversible deletes
3. **Hard Deletes for Compliance**: GDPR requirements
4. **Regular Compaction**: Scheduled cleanup
5. **Versioning**: For audit trails

## Performance Impact

- **Deletes**: Can fragment indexes
- **Updates**: Same as delete + insert
- **Compaction**: Expensive but necessary

## Pricing

Resource costs for operations and storage of deleted/versioned data.