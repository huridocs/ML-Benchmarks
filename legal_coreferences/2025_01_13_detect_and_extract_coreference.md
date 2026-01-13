

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

| Model | Samples | Tokens | Accuracy | Precision | Recall | F1 Score | Total Time (s) | Avg Time (s) |
|-------|---------|--------|----------|-----------|--------|----------|----------------|--------------|
| gemini-3-flash-preview:cloud | 10 | 355 | 0.9887 | 0.9211 | 0.9722 | 0.9459 | 53.21 | 5.32 |
| gpt-oss:20b-cloud | 10 | 355 | 0.9859 | 0.9189 | 0.9444 | 0.9315 | 61.47 | 6.15 |
| gemma3:12b | 10 | 355 | 0.9803 | 0.8372 | 1.0000 | 0.9114 | 46.06 | 4.61 |
| gpt-oss:120b-cloud | 10 | 355 | 0.9746 | 0.9091 | 0.8333 | 0.8696 | 29.27 | 2.93 |
| gemma3:4b | 10 | 355 | 0.9690 | 0.9032 | 0.7778 | 0.8358 | 12.57 | 1.26 |
| llama3.2:3b | 10 | 355 | 0.9549 | 0.8846 | 0.6389 | 0.7419 | 10.22 | 1.02 |
