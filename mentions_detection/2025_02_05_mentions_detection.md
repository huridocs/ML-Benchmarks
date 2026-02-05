# Title Extraction Benchmark Results

Date: 2026-02-03 10:44:00

| Algorithm                                              | Precision (%) | Recall (%) | F1 Score (%) | Avg Time (s) | TP | FP | FN | TN |
|--------------------------------------------------------|---------------|------------|--------------|--------------|----|----|----|----|
| Ollama gemma3:27b-cloud                                | 94.29         | 97.06      | 95.65        | 5.7727       | 33 | 2  | 1  | 84 |
| Ollama gemma3:12b                                      | 86.84         | 97.06      | 91.67        | 12.1179      | 33 | 5  | 1  | 81 |
| Regex Extractor                                        | 90.91         | 88.24      | 89.55        | 0.0001       | 30 | 3  | 4  | 83 |
| Clean stop words Regex Extractor                       | 88.24         | 88.24      | 88.24        | 0.0001       | 30 | 4  | 4  | 82 |
| WordEmbeddingExtractor_threshold_0.95                  | 90.32         | 82.35      | 86.15        | 2.5688       | 28 | 3  | 6  | 83 |
| Clean Regex Extractor                                  | 100.00        | 73.53      | 84.75        | 0.0001       | 25 | 0  | 9  | 86 |
| Fuzzy Extractor 95                                     | 90.00         | 79.41      | 84.38        | 0.0005       | 27 | 3  | 7  | 83 |
| SlidingWindowEmbeddingExtractor_threshold_0.8_stride_3 | 73.68         | 82.35      | 77.78        | 4.4107       | 28 | 10 | 6  | 76 |
| Ollama gemma3:4b                                       | 95.45         | 61.76      | 75.00        | 5.1149       | 21 | 1  | 13 | 85 |
| Embedding_threshold_0.6                                | 66.67         | 76.47      | 71.23        | 0.4496       | 26 | 13 | 8  | 73 |
| NoisyWordEmbeddingExtractor                            | 44.29         | 91.18      | 59.62        | 2.5205       | 31 | 39 | 3  | 47 |
| NGram Extractor (n=3, t=0.1)                           | 44.07         | 76.47      | 55.91        | 0.0003       | 26 | 33 | 8  | 53 |
