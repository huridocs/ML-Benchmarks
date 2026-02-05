## Test 1: `Provision` + `LegalNER-ZS`

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


| Model | Samples | Tokens | Accuracy | Precision | Recall | F1 Score | Total Time (s) | Avg Time (s) |
|-------|---------|--------|----------|-----------|--------|----------|----------------|--------------|
| gemma3:27b-cloud | 100 | 4166 | 0.9844 | 0.8800 | 0.9429 | 0.9103 | 226.89 | 2.27 |
| ministral-3:14b | 100 | 4166 | 0.9806 | 0.8854 | 0.8829 | 0.8841 | 117.06 | 1.17 |
| deepseek-r1:14b | 100 | 4166 | 0.9765 | 0.8938 | 0.8171 | 0.8537 | 1117.40 | 11.17 |
| gpt-oss | 100 | 4166 | 0.9705 | 0.7933 | 0.8771 | 0.8331 | 312.22 | 3.12 |
| deepseek-r1:8b | 100 | 4166 | 0.9700 | 0.7877 | 0.8800 | 0.8313 | 516.43 | 5.16 |
| gemma3:12b | 100 | 4166 | 0.9676 | 0.7566 | 0.9057 | 0.8244 | 111.21 | 1.11 |
| llama3.2:3b | 100 | 4166 | 0.9381 | 0.6949 | 0.4686 | 0.5597 | 40.72 | 0.41 |

## Test 2: `Case Number` + `LegalNER-ZS`


 * Dataset: https://huggingface.co/datasets/alecocc/LegalNER-ZS
 * Category: Case Number
 * Case Number text ratio: 0.8
 * Texts count: 100
 * Prompt:


```python
        prompt = f"""### ROLE
You are a Legal Document Analyst.

### TASK
Rewrite the provided text, wrapping every "Case Number" in <case_number> tags. Do not change any other text.

### DEFINITION
A "Case Number" is a unique identifier assigned to a legal case or judgment, often including year, volume, court abbreviation, or petition number (e.g., Writ Petitions, Criminal Appeals, AIR citations, SCR citations).

### EXAMPLE
* Example Input: "The judgment in Writ Petition No. 1177 of 1974 was cited."
* Example Output: "The judgment in <case_number>Writ Petition No. 1177 of 1974</case_number> was cited."

### TEXT
{text}

### FINAL RESPONSE
"""
```


| Model | Samples | Tokens | Accuracy | Precision | Recall | F1 Score | Total Time (s) | Avg Time (s) |
|-------|---------|--------|----------|-----------|--------|----------|----------------|--------------|
| gpt-oss | 100 | 3198 | 0.9631 | 0.8959 | 0.9079 | 0.9018 | 319.78 | 3.20 |
| gemma3:27b-cloud | 100 | 3198 | 0.9572 | 0.8783 | 0.8945 | 0.8863 | 222.62 | 2.23 |
| gemma3:12b | 100 | 3198 | 0.9468 | 0.8650 | 0.8476 | 0.8562 | 109.48 | 1.09 |
| deepseek-r1:14b | 100 | 3198 | 0.9481 | 0.8814 | 0.8342 | 0.8571 | 1276.24 | 12.76 |
| deepseek-r1:8b | 100 | 3198 | 0.9371 | 0.8163 | 0.8559 | 0.8357 | 519.40 | 5.19 |
| ministral-3:14b | 100 | 3198 | 0.9287 | 0.8220 | 0.7889 | 0.8051 | 97.76 | 0.98 |
| llama3.2:3b | 100 | 3198 | 0.8749 | 0.8167 | 0.4255 | 0.5595 | 39.94 | 0.40 |

## Test 3: `Court` + `LegalNER-ZS`

 * Dataset: https://huggingface.co/datasets/alecocc/LegalNER-ZS
 * Category: Court 
 * Case Number text ratio: 0.8
 * Texts count: 100
 * Prompt:


```python
        prompt = f"""### ROLE
You are a Legal Document Analyst.

### TASK
Rewrite the provided text, wrapping every "Court" entity in <court> tags. Do not change any other text.

### DEFINITION
A "Court" is a reference to a specific judicial body, tribunal, bench, or legal authority that adjudicates disputes.

### EXAMPLE
* Example Input: "The appeal was filed in the Nagpur High Court after the District Magistrate, Neemuch gave the order."
* Example Output: "The appeal was filed in the <court>Nagpur High Court</court> after the <court>District Magistrate, Neemuch</court> gave the order."

### TEXT
{text}

### FINAL RESPONSE
"""
```



| Model | Samples | Tokens | Accuracy | Precision | Recall | F1 Score | Total Time (s) | Avg Time (s) |
|-------|---------|--------|----------|-----------|--------|----------|----------------|--------------|
| gemma3:27b-cloud | 100 | 5827 | 0.9792 | 0.8410 | 0.8151 | 0.8279 | 277.11 | 2.77 |
| gpt-oss | 100 | 5827 | 0.9777 | 0.7995 | 0.8487 | 0.8234 | 383.20 | 3.83 |
| deepseek-r1:8b | 100 | 5827 | 0.9732 | 0.7544 | 0.8347 | 0.7926 | 705.53 | 7.06 |
| ministral-3:14b | 100 | 5827 | 0.9701 | 0.8256 | 0.6499 | 0.7273 | 176.36 | 1.76 |
| gemma3:12b | 100 | 5827 | 0.9662 | 0.7299 | 0.7115 | 0.7206 | 165.75 | 1.66 |
| deepseek-r1:14b | 100 | 5827 | 0.9633 | 0.6907 | 0.7255 | 0.7077 | 1165.83 | 11.66 |
| llama3.2:3b | 100 | 5827 | 0.9511 | 0.6118 | 0.5518 | 0.5803 | 58.15 | 0.58 |


