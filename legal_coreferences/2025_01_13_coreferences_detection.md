
## Test 1: Provision and examples

 * Dataset: https://huggingface.co/datasets/alecocc/LegalNER-ZS
 * Category: Provision
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in linguistic coreference resolution.

### DEFINITION
A "provision coreference" is a textual reference to a specific legal division, such as a section, sub-section, clause, article, or rule.

### EXAMPLES OF PROVISION COREFERENCES
For clarity, the following items are examples of the target pattern you are looking for:
<examples>
- Sub-section (1) of s. 195 
- Clause 13
- Section 22
- Clause (4) of Condition No. 25
- article 286 (1) (b)
- Rule 9 (2)
- S. 21
- sub-regulation (2)
- Article 311 (2)
</examples>

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a legal provision similar to the patterns shown in the <examples> block.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a provision coreference is found.
3. Respond ONLY with the word "NO" if no provision coreference is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```
 * Results:

| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| gemini-3-flash-preview:cloud | 100 | 1 | 0.9804 | 1.0000 | 295.70 | 2.96 |
| gemma3:12b | 100 | 2 | 0.9615 | 1.0000 | 71.91 | 0.72 |
| gpt-oss:120b-cloud | 100 | 2 | 0.9800 | 0.9800 | 137.32 | 1.37 |
| ministral-3:14b | 100 | 3 | 0.9796 | 0.9600 | 76.76 | 0.77 |
| mistral-large-3:675b-cloud | 100 | 3 | 0.9608 | 0.9800 | 91.02 | 0.91 |
| llama3.2:3b | 100 | 12 | 0.8167 | 0.9800 | 20.22 | 0.20 |
| gemma3:4b | 100 | 12 | 0.8276 | 0.9600 | 34.52 | 0.35 |
| nemotron-3-nano:30b-cloud | 100 | 20 | 0.9412 | 0.6400 | 48.48 | 0.48 |


## Test 2: Provision and no examples

 * Dataset: https://huggingface.co/datasets/alecocc/LegalNER-ZS
 * Category: Provision
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in linguistic coreference resolution.

### DEFINITION
A "provision coreference" is a textual reference to a specific legal division, such as a section, sub-section, clause, article, or rule.

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a legal provision similar to the patterns shown in the <examples> block.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a provision coreference is found.
3. Respond ONLY with the word "NO" if no provision coreference is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```

 * Results:


| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| gemma3:12b | 100 | 1 | 0.9804 | 1.0000 | 18.68 | 0.19 |
| ministral-3:14b | 100 | 3 | 0.9434 | 1.0000 | 11.34 | 0.11 |
| llama3.2:3b | 100 | 18 | 0.7353 | 1.0000 | 7.99 | 0.08 |


## Test 3 No examples and no mention of sections and subsections

* Dataset: https://huggingface.co/datasets/alecocc/LegalNER-ZS
 * Category: Provision
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in linguistic coreference resolution.

### DEFINITION
A "provision coreference" is a textual reference to a specific legal division, such as clause, article, or rule.

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a legal provision similar to the patterns shown in the <examples> block.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a provision coreference is found.
3. Respond ONLY with the word "NO" if no provision coreference is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```

| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| gemma3:12b | 100 | 3 | 0.9796 | 0.9600 | 66.41 | 0.66 |



## Test 4: `Case Number` with examples

* Dataset: https://huggingface.co/datasets/alecocc/LegalNER-ZS
 * Category: Case Number
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in legal entity recognition.

### DEFINITION
A "case number" or "legal citation" is a specific alphanumeric reference used to identify a court case, judgment, writ petition, appeal, or legal report. This includes standard reporter citations, petition numbers, and internal court file references.

### EXAMPLES OF CASE NUMBERS
For clarity, the following items are examples of the target pattern you are looking for:
<examples>
- (1962) 45 ITR 210 (SC)
- Writ Petition No. 1177 of 1974
- Crl.A.No. 2269 & 1663 of 2008
- AIR 1968 SC 800
- W.P. (C).No. 32721 of 2011
- [1955] 1 S.C.R. 206
- FAFO No.86 of 2010
- M.A.C.A Nos.223 and 243 of 2007-B
- MLC No.334149/12
- Misc. Criminal Application Nos.15677/2014
</examples>

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a case number or legal citation similar to the patterns shown in the <examples> block.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a case number is found.
3. Respond ONLY with the word "NO" if no case number is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```
| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| ministral-3:14b | 100 | 8 | 0.8750 | 0.9800 | 12.28 | 0.12 |
| gemma3:12b | 100 | 11 | 0.8679 | 0.9200 | 18.81 | 0.19 |
| llama3.2:3b | 100 | 17 | 0.8667 | 0.7800 | 7.99 | 0.08 |

## Test 5: `Case Number` without examples

* Dataset: https://huggingface.co/datasets/alecocc/LegalNER-ZS
 * Category: Case Number
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in legal entity recognition and court docket identification.

### DEFINITION
A "case number" is a unique alphanumeric identifier assigned to a specific lawsuit, docket, or legal matter by a court or administrative body (e.g., "Case No. 1:23-cv-00123", "No. 15-99", "Civ. Action 20-005", "Case 2:18-cr-00001").

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a specific legal case number or docket number.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a case number is found.
3. Respond ONLY with the word "NO" if no case number is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```


| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| ministral-3:14b | 100 | 7 | 0.9388 | 0.9200 | 11.37 | 0.11 |
| gemma3:12b | 100 | 13 | 0.9111 | 0.8200 | 18.16 | 0.18 |
| llama3.2:3b | 100 | 19 | 0.8974 | 0.7000 | 8.01 | 0.08 |


## Test 6: `Court` with examples

* Dataset: https://huggingface.co/datasets/alecocc/LegalNER-ZS
 * Category: Court 
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in Named Entity Recognition (NER) for judicial bodies.

### DEFINITION
A "COURT" entity is a textual reference to a specific judicial institution, tribunal, commission exercising judicial functions, or a specific bench or magistrate acting in an official capacity.

### EXAMPLES OF COURT ENTITIES
For clarity, the following items are examples of the target pattern you are looking for:
<examples>
- Supreme Court
- Nagpur High Court
- Apex Court
- National Consumer Disputes Redresal Commission
- Court of Judicial Magistrate, Hanumangarh
- Constitution Bench
- KGF Court
- District Magistrate, Neemuch
- Narmada Tribunal
</examples>

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a court or judicial body similar to the patterns shown in the <examples> block.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a court entity is found.
3. Respond ONLY with the word "NO" if no court entity is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```

| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| gemma3:12b | 100 | 6 | 0.9231 | 0.9600 | 19.36 | 0.19 |
| ministral-3:14b | 100 | 7 | 0.9057 | 0.9600 | 12.55 | 0.13 |
| llama3.2:3b | 100 | 17 | 0.7619 | 0.9600 | 8.15 | 0.08 |



## Test 7: `Court` without examples

* Dataset: https://huggingface.co/datasets/alecocc/LegalNER-ZS
 * Category: Court 
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in Named Entity Recognition (NER).

### DEFINITION
A "court mention" is a textual reference to a specific judicial body, tribunal, or adjudicatory authority. This includes specific names (e.g., "Supreme Court", "District Court"), generic references to the adjudicating body (e.g., "the Court", "this Tribunal"), or abbreviations referring to a specific court.

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a court or judicial body similar to the patterns described in the definition.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a court mention is found.
3. Respond ONLY with the word "NO" if no court mention is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```

| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| gemma3:12b | 100 | 7 | 0.9057 | 0.9600 | 18.69 | 0.19 |
| ministral-3:14b | 100 | 19 | 0.7313 | 0.9800 | 12.21 | 0.12 |
| llama3.2:3b | 100 | 31 | 0.6234 | 0.9600 | 8.12 | 0.08 |



## Test 8: `Provision` and examples - `Indian Legal NER`

 * Dataset: https://huggingface.co/datasets/hf-tuner/indian-legal-ner
 * Category: Provision
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in linguistic coreference resolution.

### DEFINITION
A "provision coreference" is a textual reference to a specific legal division, such as a section, sub-section, clause, article, or rule.

### EXAMPLES OF PROVISION COREFERENCES
For clarity, the following items are examples of the target pattern you are looking for:
<examples>
- Sub-section (1) of s. 195 
- Clause 13
- Section 22
- Clause (4) of Condition No. 25
- article 286 (1) (b)
- Rule 9 (2)
- S. 21
- sub-regulation (2)
- Article 311 (2)
</examples>

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a legal provision similar to the patterns shown in the <examples> block.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a provision coreference is found.
3. Respond ONLY with the word "NO" if no provision coreference is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```
 * Results:

| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| gemma3:12b | 100 | 8 | 0.8750 | 0.9800 | 18.57 | 0.19 |
| ministral-3:14b | 100 | 10 | 0.8333 | 1.0000 | 12.74 | 0.13 |
| llama3.2:3b | 100 | 31 | 0.6203 | 0.9800 | 8.09 | 0.08 |



## Test 9: `Provision` and no examples - `Indian Legal NER`

 * Dataset: https://huggingface.co/datasets/hf-tuner/indian-legal-ner
 * Category: Provision
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in linguistic coreference resolution.

### DEFINITION
A "provision coreference" is a textual reference to a specific legal division, such as a section, sub-section, clause, article, or rule.

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a legal provision similar to the patterns shown in the <examples> block.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a provision coreference is found.
3. Respond ONLY with the word "NO" if no provision coreference is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```

 * Results:


| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| ministral-3:14b | 100 | 21 | 0.7042 | 1.0000 | 12.63 | 0.13 |
| gemma3:12b | 100 | 23 | 0.6849 | 1.0000 | 19.58 | 0.20 |
| llama3.2:3b | 100 | 41 | 0.5556 | 0.9000 | 8.23 | 0.08 |



## Test 10: `Case Number` with examples - `Indian Legal NER`

* Dataset: https://huggingface.co/datasets/hf-tuner/indian-legal-ner
 * Category: Case Number
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in legal entity recognition.

### DEFINITION
A "case number" or "legal citation" is a specific alphanumeric reference used to identify a court case, judgment, writ petition, appeal, or legal report. This includes standard reporter citations, petition numbers, and internal court file references.

### EXAMPLES OF CASE NUMBERS
For clarity, the following items are examples of the target pattern you are looking for:
<examples>
- (1962) 45 ITR 210 (SC)
- Writ Petition No. 1177 of 1974
- Crl.A.No. 2269 & 1663 of 2008
- AIR 1968 SC 800
- W.P. (C).No. 32721 of 2011
- [1955] 1 S.C.R. 206
- FAFO No.86 of 2010
- M.A.C.A Nos.223 and 243 of 2007-B
- MLC No.334149/12
- Misc. Criminal Application Nos.15677/2014
</examples>

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a case number or legal citation similar to the patterns shown in the <examples> block.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a case number is found.
3. Respond ONLY with the word "NO" if no case number is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```

| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| ministral-3:14b | 100 | 18 | 0.7581 | 0.9400 | 12.84 | 0.13 |
| gemma3:12b | 100 | 24 | 0.7097 | 0.8800 | 19.54 | 0.20 |
| llama3.2:3b | 100 | 29 | 0.6667 | 0.8400 | 8.42 | 0.08 |




## Test 11: `Case Number` without examples - `Indian Legal NER`

* Dataset: https://huggingface.co/datasets/hf-tuner/indian-legal-ner
 * Category: Case Number
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in legal entity recognition and court docket identification.

### DEFINITION
A "case number" is a unique alphanumeric identifier assigned to a specific lawsuit, docket, or legal matter by a court or administrative body (e.g., "Case No. 1:23-cv-00123", "No. 15-99", "Civ. Action 20-005", "Case 2:18-cr-00001").

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a specific legal case number or docket number.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a case number is found.
3. Respond ONLY with the word "NO" if no case number is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```

| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| ministral-3:14b | 100 | 24 | 0.7241 | 0.8400 | 13.02 | 0.13 |
| gemma3:12b | 100 | 24 | 0.7407 | 0.8000 | 19.28 | 0.19 |
| llama3.2:3b | 100 | 27 | 0.7170 | 0.7600 | 8.12 | 0.08 |



## Test 12: `Court` with examples - `Indian Legal NER`

* Dataset: https://huggingface.co/datasets/hf-tuner/indian-legal-ner
 * Category: Court 
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in Named Entity Recognition (NER) for judicial bodies.

### DEFINITION
A "COURT" entity is a textual reference to a specific judicial institution, tribunal, commission exercising judicial functions, or a specific bench or magistrate acting in an official capacity.

### EXAMPLES OF COURT ENTITIES
For clarity, the following items are examples of the target pattern you are looking for:
<examples>
- Supreme Court
- Nagpur High Court
- Apex Court
- National Consumer Disputes Redresal Commission
- Court of Judicial Magistrate, Hanumangarh
- Constitution Bench
- KGF Court
- District Magistrate, Neemuch
- Narmada Tribunal
</examples>

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a court or judicial body similar to the patterns shown in the <examples> block.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a court entity is found.
3. Respond ONLY with the word "NO" if no court entity is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```

| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| ministral-3:14b | 100 | 12 | 0.8065 | 1.0000 | 13.60 | 0.14 |
| gemma3:12b | 100 | 13 | 0.7937 | 1.0000 | 20.41 | 0.20 |
| llama3.2:3b | 100 | 25 | 0.6712 | 0.9800 | 8.39 | 0.08 |




## Test 13: `Court` without examples - `Indian Legal NER`

* Dataset: https://huggingface.co/datasets/hf-tuner/indian-legal-ner
 * Category: Court 
 * Prompt:

```python
        prompt = f"""
### ROLE
You are a precise Legal Document Analyst specializing in Named Entity Recognition (NER).

### DEFINITION
A "court mention" is a textual reference to a specific judicial body, tribunal, or adjudicatory authority. This includes specific names (e.g., "Supreme Court", "District Court"), generic references to the adjudicating body (e.g., "the Court", "this Tribunal"), or abbreviations referring to a specific court.

### TASK
Analyze the text provided in the <target_text> tags below. Determine if the text contains any mentions of a court or judicial body similar to the patterns described in the definition.

### CONSTRAINTS
1. Your output must be binary. 
2. Respond ONLY with the word "YES" if a court mention is found.
3. Respond ONLY with the word "NO" if no court mention is found.
4. Do not provide explanations, citations, or introductory text.

### TARGET TEXT
<target_text>
{text}
</target_text>

FINAL RESPONSE:
"""
```

| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|-------|---------|----------|-----------|--------|----------------|--------------|
| gemma3:12b | 100 | 8 | 0.8621 | 1.0000 | 20.23 | 0.20 |
| ministral-3:14b | 100 | 21 | 0.7042 | 1.0000 | 13.98 | 0.14 |
| llama3.2:3b | 100 | 34 | 0.5952 | 1.0000 | 11.98 | 0.12 |




### Average of `with examples` results:

| Model | Samples | Mistakes | Precision | Recall | Total Time (s) | Avg Time (s) |
|:---|---:|---:|---:|---:|---:|---:|
| ministral-3:14b | 100 | 9.6667 | 0.8597 | 0.9733 | 23.4617 | 0.2367 |
| gemma3:12b | 100 | 10.6667 | 0.8552 | 0.9567 | 28.1000 | 0.2817 |
| llama3.2:3b | 100 | 21.8333 | 0.7339 | 0.9200 | 10.2100 | 0.1000 |