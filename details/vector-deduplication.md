## Overview

Vector deduplication identifies and removes duplicate or near-duplicate entries based on embedding similarity. Critical for data quality, storage efficiency, and preventing redundant search results.

## Why Deduplicate?

### Problems with Duplicates
- **Redundant Results**: Same content appears multiple times
- **Wasted Storage**: Unnecessary vectors and metadata
- **Search Quality**: Reduces diversity of results
- **Processing Costs**: Redundant embeddings and indexing
- **User Experience**: Confusing repeated content

### Common Sources
- Scraped web data
- Document versions
- Copy-paste content
- Reformatted text
- Translated variants

## Detection Methods

### Exact Duplicates
Identical vectors:
```python
import numpy as np

def find_exact_duplicates(vectors):
    seen = {}
    duplicates = []
    for i, vec in enumerate(vectors):
        key = vec.tobytes()
        if key in seen:
            duplicates.append((i, seen[key]))
        else:
            seen[key] = i
    return duplicates
```

### Near-Duplicates
Similar vectors above threshold:
```python
def find_near_duplicates(vectors, threshold=0.98):
    duplicates = []
    for i, vec_i in enumerate(vectors):
        for j, vec_j in enumerate(vectors[i+1:], start=i+1):
            similarity = cosine_similarity(vec_i, vec_j)
            if similarity > threshold:
                duplicates.append((i, j, similarity))
    return duplicates
```

### Clustering-Based
Group similar vectors:
```python
from sklearn.cluster import DBSCAN

def cluster_duplicates(vectors, eps=0.1, min_samples=2):
    clustering = DBSCAN(eps=eps, min_samples=min_samples, metric='cosine')
    labels = clustering.fit_predict(vectors)
    
    # Group by cluster
    clusters = {}
    for idx, label in enumerate(labels):
        if label != -1:  # Not noise
            clusters.setdefault(label, []).append(idx)
    return clusters
```

## Similarity Thresholds

Typical values:
- **0.99+**: Nearly identical (minor formatting differences)
- **0.95-0.99**: Very similar (paraphrases, versions)
- **0.90-0.95**: Similar (related content)
- **<0.90**: Different content

### Choosing Threshold
Factors:
- Content type (technical vs narrative)
- Acceptable similarity level
- False positive tolerance
- Business requirements

## Deduplication Strategies

### Keep First
Retain earliest entry:
```python
def deduplicate_keep_first(vectors, metadata, threshold=0.98):
    keep = []
    removed = []
    
    for i, vec in enumerate(vectors):
        is_duplicate = False
        for kept_idx in keep:
            if cosine_similarity(vec, vectors[kept_idx]) > threshold:
                is_duplicate = True
                removed.append((i, kept_idx))
                break
        if not is_duplicate:
            keep.append(i)
    
    return keep, removed
```

### Keep Best Quality
Retain highest quality:
```python
def deduplicate_keep_best(vectors, scores, threshold=0.98):
    # Sort by quality score
    sorted_indices = sorted(range(len(vectors)), 
                          key=lambda i: scores[i], 
                          reverse=True)
    
    keep = []
    for idx in sorted_indices:
        is_duplicate = any(
            cosine_similarity(vectors[idx], vectors[kept]) > threshold
            for kept in keep
        )
        if not is_duplicate:
            keep.append(idx)
    
    return keep
```

### Merge Metadata
Combine information:
```python
def merge_duplicates(duplicate_groups, metadata):
    merged = []
    for group in duplicate_groups:
        # Take first vector
        representative = group[0]
        
        # Merge metadata
        merged_meta = {
            "primary_id": metadata[representative]["id"],
            "duplicate_ids": [metadata[i]["id"] for i in group[1:]],
            "sources": list(set(
                metadata[i].get("source") for i in group
            )),
            "combined_content": " | ".join(
                metadata[i]["content"] for i in group
            )
        }
        merged.append((representative, merged_meta))
    
    return merged
```

## Scalable Approaches

### MinHash/LSH
For large datasets:
```python
from datasketch import MinHash, MinHashLSH

def lsh_deduplication(texts, threshold=0.9):
    lsh = MinHashLSH(threshold=threshold, num_perm=128)
    
    # Create MinHash for each text
    minhashes = {}
    for i, text in enumerate(texts):
        m = MinHash(num_perm=128)
        for word in text.split():
            m.update(word.encode('utf8'))
        minhashes[i] = m
        lsh.insert(i, m)
    
    # Find duplicates
    duplicates = []
    for i, m in minhashes.items():
        result = lsh.query(m)
        if len(result) > 1:
            duplicates.append(result)
    
    return duplicates
```

### Batch Processing
Process in chunks:
```python
def batch_deduplicate(vectors, batch_size=1000, threshold=0.98):
    n = len(vectors)
    keep_mask = np.ones(n, dtype=bool)
    
    for i in range(0, n, batch_size):
        batch = vectors[i:i+batch_size]
        # Compare batch against kept vectors
        kept_vectors = vectors[keep_mask]
        similarities = cosine_similarity(batch, kept_vectors)
        
        # Mark duplicates
        max_sims = similarities.max(axis=1)
        keep_mask[i:i+batch_size] = max_sims < threshold
    
    return np.where(keep_mask)[0]
```

## Production Workflow

### During Ingestion
```python
def ingest_with_dedup(new_documents, existing_db, threshold=0.98):
    # Generate embeddings
    new_embeddings = embed(new_documents)
    
    # Check against existing
    for i, emb in enumerate(new_embeddings):
        results = existing_db.search(emb, k=1)
        if results[0].score > threshold:
            # Duplicate found
            print(f"Skipping duplicate: {new_documents[i].id}")
            continue
        
        # Not a duplicate, add
        existing_db.upsert(emb, new_documents[i])
```

### Periodic Cleanup
```python
def periodic_dedup(db, threshold=0.98):
    # Export all vectors
    all_vectors = db.export_vectors()
    
    # Find duplicates
    keep_indices = deduplicate_keep_best(
        all_vectors.embeddings,
        all_vectors.quality_scores,
        threshold
    )
    
    # Delete duplicates
    all_indices = set(range(len(all_vectors)))
    remove_indices = all_indices - set(keep_indices)
    
    db.delete(list(remove_indices))
    print(f"Removed {len(remove_indices)} duplicates")
```

## Monitoring

### Metrics
- Duplicate rate: % of vectors that are duplicates
- Threshold distribution: Similarity of detected duplicates
- Storage saved: Reduction in vector count
- Quality impact: Search performance before/after

### Reporting
```python
def dedup_report(duplicates, threshold):
    return {
        "total_duplicates": len(duplicates),
        "threshold": threshold,
        "avg_similarity": np.mean([d[2] for d in duplicates]),
        "max_similarity": max(d[2] for d in duplicates),
        "min_similarity": min(d[2] for d in duplicates),
        "storage_saved_pct": len(duplicates) / total_vectors * 100
    }
```

## Best Practices

1. **Set Appropriate Threshold**: Too high misses dups, too low false positives
2. **Test on Sample**: Verify threshold before full dedup
3. **Keep Quality**: Retain best version when merging
4. **Log Decisions**: Track what was removed and why
5. **Gradual Rollout**: Test on subset first
6. **Monitor Impact**: Track search quality changes
7. **Preserve Provenance**: Keep duplicate IDs for auditing

## Trade-offs

**Benefits:**
- Reduced storage costs
- Better search diversity
- Improved user experience
- Lower processing overhead

**Risks:**
- False positives (removing unique content)
- Processing time for large datasets
- Complexity in threshold selection
- Potential information loss

## Pricing

Deduplication saves storage costs; processing overhead is one-time per vector.