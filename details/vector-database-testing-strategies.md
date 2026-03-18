## Why Test Vector Databases?

- Prevent regressions
- Validate correctness
- Ensure performance
- Build confidence
- Enable safe deployments

## Testing Pyramid

```
     /\
    /  \ E2E Tests (few)
   /----\
  / Int. \ Integration Tests (some)
 /--------\
/  Unit   \ Unit Tests (many)
----------
```

## Unit Tests

**What to Test**:

**Embedding Generation**:
```python
def test_embedding_generation():
    text = "test input"
    embedding = generate_embedding(text)
    
    assert embedding is not None
    assert len(embedding) == EXPECTED_DIM
    assert all(isinstance(x, float) for x in embedding)
    assert is_normalized(embedding)
```

**Distance Calculations**:
```python
def test_cosine_similarity():
    v1 = [1, 0, 0]
    v2 = [1, 0, 0]
    v3 = [0, 1, 0]
    
    assert cosine_similarity(v1, v2) == 1.0
    assert cosine_similarity(v1, v3) == 0.0
```

**Data Validation**:
```python
def test_metadata_validation():
    invalid_metadata = {"user_id": None}
    with pytest.raises(ValidationError):
        validate_metadata(invalid_metadata)
```

## Integration Tests

**Database Operations**:
```python
def test_insert_and_search():
    # Insert
    db.insert(id="1", vector=[0.1, 0.2], metadata={...})
    
    # Search
    results = db.search(query_vector=[0.1, 0.2], k=1)
    
    assert len(results) == 1
    assert results[0].id == "1"
    assert results[0].score > 0.99
```

**Filter Testing**:
```python
def test_filtered_search():
    # Insert multiple vectors
    db.insert_many(vectors_with_metadata)
    
    # Search with filter
    results = db.search(
        query_vector,
        k=10,
        filter={"category": "tech"}
    )
    
    assert all(r.metadata["category"] == "tech" for r in results)
```

**CRUD Operations**:
```python
def test_update_and_delete():
    # Insert
    db.insert("1", vector, metadata)
    
    # Update
    db.update("1", new_metadata={"updated": True})
    result = db.get("1")
    assert result.metadata["updated"] is True
    
    # Delete
    db.delete("1")
    assert db.get("1") is None
```

## Retrieval Quality Tests

**Recall Testing**:
```python
def test_recall_at_k():
    # Insert known dataset
    ground_truth = setup_known_dataset()
    
    for query, expected in ground_truth:
        results = db.search(query, k=10)
        actual = [r.id for r in results]
        
        recall = len(set(actual) & set(expected)) / len(expected)
        assert recall > 0.9, f"Recall too low: {recall}"
```

**Semantic Quality**:
```python
def test_semantic_search():
    # Known similar documents
    db.insert("doc1", embed("Python programming"), {...})
    db.insert("doc2", embed("Python coding"), {...})
    db.insert("doc3", embed("JavaScript development"), {...})
    
    results = db.search(embed("Python development"), k=2)
    
    # Should return Python docs, not JavaScript
    assert "doc1" in [r.id for r in results]
    assert "doc2" in [r.id for r in results]
```

## Performance Tests

**Latency Benchmarks**:
```python
def test_query_latency():
    latencies = []
    for _ in range(1000):
        start = time.perf_counter()
        db.search(random_vector(), k=10)
        latencies.append(time.perf_counter() - start)
    
    p95 = np.percentile(latencies, 95)
    assert p95 < 0.1, f"p95 latency too high: {p95}s"
```

**Throughput Testing**:
```python
def test_concurrent_queries():
    with ThreadPoolExecutor(max_workers=10) as executor:
        futures = []
        start = time.time()
        
        for _ in range(1000):
            futures.append(executor.submit(db.search, vector, k=10))
        
        results = [f.result() for f in futures]
        duration = time.time() - start
        
        qps = len(results) / duration
        assert qps > 100, f"QPS too low: {qps}"
```

**Index Build Performance**:
```python
def test_index_build_time():
    vectors = generate_test_vectors(100000)
    
    start = time.time()
    db.insert_many(vectors)
    db.build_index()
    duration = time.time() - start
    
    assert duration < 300, f"Index build too slow: {duration}s"
```

## Load Tests

**Sustained Load**:
```python
def test_sustained_load():
    """Run queries for 5 minutes, check for degradation"""
    end_time = time.time() + 300
    latencies = []
    
    while time.time() < end_time:
        start = time.perf_counter()
        db.search(random_vector(), k=10)
        latencies.append(time.perf_counter() - start)
        time.sleep(0.01)
    
    # Check no degradation over time
    early = np.mean(latencies[:100])
    late = np.mean(latencies[-100:])
    assert late / early < 1.5, "Performance degraded"
```

## Chaos Engineering

**Network Failures**:
```python
def test_network_partition():
    with simulate_network_failure():
        with pytest.raises(ConnectionError):
            db.search(vector, k=10)
    
    # Should recover
    results = db.search(vector, k=10)
    assert len(results) == 10
```

**Resource Exhaustion**:
```python
def test_memory_pressure():
    # Fill memory
    with high_memory_pressure():
        # Should still work, maybe slower
        results = db.search(vector, k=10)
        assert results is not None
```

**Data Corruption**:
```python
def test_corrupt_data_handling():
    # Insert valid data
    db.insert("1", valid_vector, metadata)
    
    # Simulate corruption
    corrupt_database_file()
    
    # Should detect and handle
    with pytest.raises(DataCorruptionError):
        db.search(vector, k=10)
```

## Regression Testing

**Golden Dataset**:
```python
def test_against_golden_dataset():
    """Test against known query-result pairs"""
    golden = load_golden_dataset()
    
    for query, expected_results in golden:
        actual = db.search(query, k=len(expected_results))
        
        # Check if results match (order may vary)
        assert set(r.id for r in actual) == set(expected_results)
```

## CI/CD Integration

**Pre-Commit**:
- Unit tests
- Linting
- Fast integration tests

**Pull Request**:
- All unit tests
- Integration tests
- Performance smoke tests

**Pre-Deploy**:
- Full integration suite
- Performance benchmarks
- Load tests

**Post-Deploy**:
- Smoke tests
- Canary monitoring
- Rollback tests

## Test Data Management

**Fixtures**:
```python
@pytest.fixture
def test_db():
    db = create_test_database()
    yield db
    db.cleanup()

@pytest.fixture
def sample_vectors():
    return generate_test_vectors(100)
```

**Test Isolation**:
- Separate test database
- Clean state between tests
- No dependencies between tests

## Monitoring Tests

**Synthetic Monitoring**:
```python
def test_production_health():
    """Run in production as health check"""
    result = db.search(known_vector, k=1)
    assert result[0].id == expected_id
    assert result[0].score > 0.95
```

## Best Practices

1. **Test at Multiple Levels**: Unit → Integration → E2E
2. **Use Realistic Data**: Match production distribution
3. **Test Edge Cases**: Empty results, large K, etc.
4. **Monitor Test Performance**: Tests should be fast
5. **Maintain Golden Datasets**: Version controlled
6. **Automate Everything**: CI/CD integration
7. **Test Failures**: Not just happy path
8. **Performance Baselines**: Track over time
9. **Regular Review**: Keep tests relevant
10. **Document Intent**: Why test exists

## Common Pitfalls

- Testing only happy paths
- Ignoring performance tests
- Flaky tests (timing issues)
- Over-mocking (not testing real DB)
- No test data management
- Tests too slow (discourages running)
- Not testing at scale
- Missing edge cases