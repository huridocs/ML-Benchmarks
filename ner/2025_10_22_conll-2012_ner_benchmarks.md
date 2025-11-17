The code is in NER-in-docker/src/drivers/benchmarks/benchmark_ner.py


## Entity Counts

| Entity Type | Ground Truth |
|-------------|--------------|
| PERSON | 10 |
| LOCATION | 14 |
| ORGANIZATION | 11 |

## Model Performance Comparison

| Model | Overall Precision | Overall Recall | Overall F1 Score | Total Time (s) | PERSON F1 | LOCATION F1 | ORGANIZATION F1 |
|-------|-------------------|----------------|------------------|----------------|-----------|-------------|-----------------|
| REST API | 100.00% | 100.00% | 100.00% | 5.80 | 100.00% | 100.00% | 100.00% |
| GPT (gpt-oss:20b) | 93.75% | 85.71% | 89.55% | 81.56 | 90.00% | 88.89% | 90.00% |
| Qwen (qwen3:14b) | 93.55% | 82.86% | 87.88% | 65.12 | 90.00% | 84.62% | 90.00% |
| Deepseek (deepseek-r1:14b) | 96.43% | 77.14% | 85.71% | 30.39 | 90.00% | 78.26% | 90.00% |
| Llama (llama3.1:8b) | 86.67% | 74.29% | 80.00% | 3.97 | 90.00% | 78.26% | 72.73% |

### Key Findings

- **Best Overall Performance**: REST API (100% across all metrics)
- **Best LLM Performance**: GPT (gpt-oss:20b) with 89.55% F1 score
- **Fastest LLM**: Llama (llama3.1:8b) at 3.97 seconds
- **Best Speed/Performance Ratio**: Deepseek (deepseek-r1:14b) with 85.71% F1 in 30.39 seconds



================================================================================
REST API (http://localhost:5070/) BENCHMARK RESULTS
================================================================================

**Dataset:** OntoNotes 5.0 (CoNLL-2012)  
**Target:** 10 entities per type  
**Entity types:** PERSON, LOCATION, ORGANIZATION

| Entity Type | Precision | Recall | F1 Score | TP | FP | FN |
|-------------|-----------|--------|----------|----|----|-----|
| PERSON | 100.00% | 100.00% | 100.00% | 10 | 0 | 0 |
| LOCATION | 100.00% | 100.00% | 100.00% | 14 | 0 | 0 |
| ORGANIZATION | 100.00% | 100.00% | 100.00% | 11 | 0 | 0 |
| **OVERALL** | **100.00%** | **100.00%** | **100.00%** | **35** | **0** | **0** |

**Total time:** 5.80 seconds



================================================================================
Llama LLM (llama3.1:8b) BENCHMARK RESULTS
================================================================================

**Dataset:** OntoNotes 5.0 (CoNLL-2012)  
**Target:** 10 entities per type  
**Entity types:** PERSON, LOCATION, ORGANIZATION

**Evaluation Method:** Fuzzy Matching
- Character overlap threshold: 50%
- Text similarity threshold: 80%

| Entity Type | Precision | Recall | F1 Score | TP | FP | FN |
|-------------|-----------|--------|----------|----|----|-----|
| PERSON | 90.00% | 90.00% | 90.00% | 9 | 1 | 1 |
| LOCATION | 100.00% | 64.29% | 78.26% | 9 | 0 | 5 |
| ORGANIZATION | 72.73% | 72.73% | 72.73% | 8 | 3 | 3 |
| **OVERALL** | **86.67%** | **74.29%** | **80.00%** | **26** | **4** | **9** |

**Total time:** 3.97 seconds



================================================================================
GPT LLM (gpt-oss:20b) BENCHMARK RESULTS
================================================================================

**Dataset:** OntoNotes 5.0 (CoNLL-2012)  
**Target:** 10 entities per type  
**Entity types:** PERSON, LOCATION, ORGANIZATION

**Evaluation Method:** Fuzzy Matching
- Character overlap threshold: 50%
- Text similarity threshold: 80%

| Entity Type | Precision | Recall | F1 Score | TP | FP | FN |
|-------------|-----------|--------|----------|----|----|-----|
| PERSON | 90.00% | 90.00% | 90.00% | 9 | 1 | 1 |
| LOCATION | 92.31% | 85.71% | 88.89% | 12 | 1 | 2 |
| ORGANIZATION | 100.00% | 81.82% | 90.00% | 9 | 0 | 2 |
| **OVERALL** | **93.75%** | **85.71%** | **89.55%** | **30** | **2** | **5** |

**Total time:** 81.56 seconds


================================================================================
Deepseek LLM (deepseek-r1:14b) BENCHMARK RESULTS
================================================================================

**Dataset:** OntoNotes 5.0 (CoNLL-2012)  
**Target:** 10 entities per type  
**Entity types:** PERSON, LOCATION, ORGANIZATION

**Evaluation Method:** Fuzzy Matching
- Character overlap threshold: 50%
- Text similarity threshold: 80%

| Entity Type | Precision | Recall | F1 Score | TP | FP | FN |
|-------------|-----------|--------|----------|----|----|-----|
| PERSON | 90.00% | 90.00% | 90.00% | 9 | 1 | 1 |
| LOCATION | 100.00% | 64.29% | 78.26% | 9 | 0 | 5 |
| ORGANIZATION | 100.00% | 81.82% | 90.00% | 9 | 0 | 2 |
| **OVERALL** | **96.43%** | **77.14%** | **85.71%** | **27** | **1** | **8** |

**Total time:** 30.39 seconds


================================================================================
Qwen LLM (qwen3:14b) BENCHMARK RESULTS
================================================================================

**Dataset:** OntoNotes 5.0 (CoNLL-2012)  
**Target:** 10 entities per type  
**Entity types:** PERSON, LOCATION, ORGANIZATION

**Evaluation Method:** Fuzzy Matching
- Character overlap threshold: 50%
- Text similarity threshold: 80%

| Entity Type | Precision | Recall | F1 Score | TP | FP | FN |
|-------------|-----------|--------|----------|----|----|-----|
| PERSON | 90.00% | 90.00% | 90.00% | 9 | 1 | 1 |
| LOCATION | 91.67% | 78.57% | 84.62% | 11 | 1 | 3 |
| ORGANIZATION | 100.00% | 81.82% | 90.00% | 9 | 0 | 2 |
| **OVERALL** | **93.55%** | **82.86%** | **87.88%** | **29** | **2** | **6** |

**Total time:** 65.12 seconds
