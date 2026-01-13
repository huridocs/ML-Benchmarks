

 * Dataset: https://huggingface.co/datasets/alecocc/LegalNER-ZS
 * Category: Provision
 * Provision text ratio: 0.8
 * Texts count: 10
 * Prompt:


```python
        prompt = f"""### ROLE
You are a Legal Document Analyst.

### TASK
Rewrite the provided text, wrapping every "Provision Reference" in <prov> tags. Do not change any other text.

### DEFINITION
A "provision coreference" is a textual reference to a specific legal division, such as a section, sub-section, clause, article, or rule.

### EXAMPLE
* Example Input: "We cite Article 12 and Section 4."
* Example Output: "We cite <prov>Article 12</prov> and <prov>Section 4</prov>."

### TEXT
{text}

### FINAL RESPONSE
"""
```

| Model | Samples | Tokens | Accuracy | Estimated Mistakes | Precision | Recall | F1 Score | Total Time (s) | Avg Time (s) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **gemma3:27b-cloud** | 10 | 355 | 99.15% | 3 | 92.31% | 100.00% | 96.00% | 17.09 | 1.71 |
| **gemini-3-flash-preview:cloud** | 10 | 355 | 98.87% | 4 | 92.11% | 97.22% | 94.59% | 53.21 | 5.32 |
| **deepseek-r1:14b** | 10 | 355 | 98.87% | 4 | 92.11% | 97.22% | 94.59% | 101.00 | 10.15 |
| **gpt-oss:20b-cloud** | 10 | 355 | 98.59% | 5 | 91.89% | 94.44% | 93.15% | 61.47 | 6.15 |
| **gemma3:12b** | 10 | 355 | 98.03% | 7 | 83.72% | 100.00% | 91.14% | 46.06 | 4.61 |
| **deepseek-r1:8b** | 10 | 355 | 97.75% | 8 | 81.82% | 100.00% | 90.00% | 139.04 | 13.90 |
| **gpt-oss:120b-cloud** | 10 | 355 | 97.46% | 9 | 90.91% | 83.33% | 86.96% | 29.27 | 2.93 |
| **gemma3:4b** | 10 | 355 | 96.90% | 11 | 90.32% | 77.78% | 83.58% | 12.57 | 1.26 |
| **llama3.2:3b** | 10 | 355 | 95.49% | 16 | 88.46% | 63.89% | 74.19% | 10.22 | 1.02 |
| **llama3.1:8b** | 10 | 355 | 90.14% | 35 | 66.67% | 5.56% | 10.26% | 25.63 | 2.56 |
| **mistral:7b** | 10 | 355 | 89.58% | 37 | 48.84% | 58.33% | 53.16% | 17.83 | 1.78 |
