# Embedding Model Benchmark Results

**Test Date:** 2025-11-25 18:34:30

**Number of Documents:** 500

**Models Tested:** 1

**Data Source:** data/uwazi_data.json

**Save to Collection:** True

## Summary

|       Model      |Status|Docs| Dim|Load (s)|Avg Embed (s)|Throughput (docs/s)|Total (s)|Memory (MB)|
|------------------|------|----|----|--------|-------------|-------------------|---------|-----------|
|qwen3-embedding:8b|   ✓  | 500|4096|  0.04  |    0.0235   |       42.52       |  15.07  |   135.17  |

## Detailed Results

|       Model      |    Short Name    |         Collection         |Documents|Embedding Dim|Load Time (s)|Avg Embed Time (s)|Min Embed Time (s)|Max Embed Time (s)|Total Embed Time (s)|Throughput (docs/s)|Storage Time (s)|Avg Search Time (s)|Total Time (s)|Memory (MB)|CPU (%)|Status|
|------------------|------------------|----------------------------|---------|-------------|-------------|------------------|------------------|------------------|--------------------|-------------------|----------------|-------------------|--------------|-----------|-------|------|
|qwen3-embedding:8b|qwen3-embedding:8b|documents_qwen3_embedding_8b|   500   |     4096    |     0.04    |      0.0235      |      0.0221      |       0.025      |        11.76       |       42.52       |      0.74      |       0.0656      |     15.07    |   135.17  |  1.1  |   ✓  |

## Metrics Explanation

- **Model**: Full HuggingFace model name
- **Short Name**: Shortened model name for display
- **Collection**: Qdrant collection name where embeddings are stored
- **Documents**: Number of documents processed
- **Embedding Dim**: Dimension of the embedding vectors
- **Load Time**: Time to load the model and tokenizer
- **Avg Embed Time**: Average time to generate one embedding
- **Min/Max Embed Time**: Fastest and slowest embedding generation times
- **Total Embed Time**: Total time to generate all embeddings
- **Throughput**: Number of documents processed per second
- **Storage Time**: Time to store embeddings in Qdrant
- **Avg Search Time**: Average time for semantic search queries
- **Total Time**: Total benchmark time including all operations
- **Memory**: Additional memory consumed by the model
- **CPU**: CPU usage during benchmark
- **Status**: Success (✓) or failure (✗) status


## Performance Rankings

**Fastest Embedding:** qwen3-embedding:8b (0.0235s/doc)

**Highest Throughput:** qwen3-embedding:8b (42.52 docs/s)

**Lowest Memory:** qwen3-embedding:8b (135.17 MB)

**Fastest Search:** qwen3-embedding:8b (0.0656s)

