# Model Evaluation Report: `gemma3:12b`

## ✅ Correctly Predicted Samples

The model successfully extracted the following legal provisions:

| Sample | Text Excerpt | Extracted Provision |
| --- | --- | --- |
| **[1]** | "...specifies under **Rule 8** four classes..." | `Rule 8` |
| **[2]** | "The waiver under **S. 21** is limited..." | `S. 21` |
| **[3]** | "...expression 'restriction' under **Article 304**." | `Article 304` |

---

## ❌ Sample Mistakes (Token-level)

The following samples contain **False Positives**, where the model identified tokens as part of a provision that were not in the ground truth.

### [Sample 6]

> **Text:** In Suraj Bhan Meena (Supra) and Rajesh Kumar (Supra) also the Apex Court has followed the decision in M. Nagaraj (Supra) and has accepted that „ backwardness‟ is a prerequisite for providing the benefit under **Article 16 (4-A)** of the Constitution.

* **Error:** Token 6 (`Supra`) → **FALSE POSITIVE** (Model tagged it, but it shouldn't be a provision).

### [Sample 8]

> **Text:** ...investigating the question whether there was violation of procedure contained in **Clause 8 (vi) (a)** of the College Code.

| Token | Content | Error Type | Details |
| --- | --- | --- | --- |
| 41 | `(` | **False Positive** | Predicted=True, Truth=False |
| 42 | `a` | **False Positive** | Predicted=True, Truth=False |
| 43 | `)` | **False Positive** | Predicted=True, Truth=False |

### [Sample 10]

> **Text:** To this, Mr. Setalvad argued that if the building was equipped with **machinery** for the purpose of running a textile mill...

* **Error:** Token 14 (`machinery`) → **FALSE POSITIVE** (General noun incorrectly identified as a provision).

---

## 📊 Performance Summary

| Metric | Result |
| --- | --- |
| **Total Samples** | 10 |
| **Total Tokens** | 355 |
| **Token Accuracy** | 98.59% |
| **Precision** | 0.8780 |
| **Recall** | 1.0000 |
| **F1 Score** | 0.9351 |

### ⏱️ Execution Timing

* **Total Time:** 45.67s
* **Average Time per Text:** 4.57s

---

**Observations:**
The model has a **perfect Recall (1.0)**, meaning it never misses a provision, but it suffers from **lower Precision** due to over-tagging (False Positives) on words like "Supra" or common nouns like "machinery."
