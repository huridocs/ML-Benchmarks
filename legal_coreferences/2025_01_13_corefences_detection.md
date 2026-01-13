
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
| gemma3:12b | 100 | 2 | 0.9615 | 1.0000 | 66.20 | 0.66 |


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