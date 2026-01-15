### Summary of Best Models for Detection

| Task | Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Provision** | gemini-3-flash-preview:cloud | 100 | 1 | 0.9804 | 1.0000 | 295.70 | 2.96 |
| **Provision** | gemma3:12b | 100 | 2 | 0.9615 | 1.0000 | 71.91 | 0.72 |
| **Case Number** | ministral-3:14b | 100 | 8 | 0.8750 | 0.9800 | 12.28 | 0.12 |
| **Court** | gemma3:12b | 100 | 6 | 0.9231 | 0.9600 | 19.36 | 0.19 |
| **Provision (Indian Legal NER)** | gemma3:12b | 100 | 8 | 0.8750 | 0.9800 | 18.57 | 0.19 |
| **Case Number (Indian Legal NER)** | ministral-3:14b | 100 | 18 | 0.7581 | 0.9400 | 12.84 | 0.13 |
| **Court (Indian Legal NER)** | ministral-3:14b | 100 | 12 | 0.8065 | 1.0000 | 13.60 | 0.14 |




### Best Models for Detect & Extract:

| Task  | Model | Samples | Tokens | Accuracy | Precision | Recall | F1 Score | Total Time (s) | Avg Time (s) |
|-------|-------|---------|--------|----------|-----------|--------|----------|----------------|--------------|
| **Provision** | gemma3:27b-cloud | 100 | 4166 | 0.9844 | 0.8800 | 0.9429 | 0.9103 | 226.89 | 2.27 |
| **Case Number** | gpt-oss | 100 | 3198 | 0.9631 | 0.8959 | 0.9079 | 0.9018 | 319.78 | 3.20 |
| **Court** | gemma3:27b-cloud | 100 | 5827 | 0.9792 | 0.8410 | 0.8151 | 0.8279 | 277.11 | 2.77 |



