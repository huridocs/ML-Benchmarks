
# Model Evaluation Report: gemma3:12b

## ✅ Correctly Predicted Samples

*(No samples to display)*

---

## ❌ Sample Mistakes

The following samples contain token-level discrepancies between predicted and true values.

### [Sample 1]

> **Text:** The admission form which was signed by respondent Subodh Chandra Bose specifies under Rule 8 four classes of paying beds with varying charges, the charge for Sanat Chandra Bose being Rs. 225/- per month.

| Token | Content | Error Type | Details |
| --- | --- | --- | --- |
| 14 | `Rule` | **False Negative** | Predicted=False, Truth=True |
| 15 | `8` | **False Negative** | Predicted=False, Truth=True |
| 33 | `.` | **False Positive** | Predicted=True, Truth=False |
| 37 | `.` | **False Positive** | Predicted=True, Truth=False |

### [Sample 2]

> **Text:** The waiver under S. 21 is limited to objection in the appellate and revisional Courts.

| Token | Content | Error Type | Details |
| --- | --- | --- | --- |
| 4 | `S.` | **False Negative** | Predicted=False, Truth=True |
| 5 | `21` | **False Negative** | Predicted=False, Truth=True |
| 16 | `.` | **False Positive** | Predicted=True, Truth=False |

### [Sample 3]

> **Text:** He has further contended that tax is a 'restriction' on free trade and there is no reason why a different meaning should be given to the expression 'restriction' under Article 304.

| Token | Content | Error Type | Details |
| --- | --- | --- | --- |
| 32 | `Article` | **False Negative** | Predicted=False, Truth=True |
| 33 | `304` | **False Negative** | Predicted=False, Truth=True |
| 34 | `.` | **False Positive** | Predicted=True, Truth=False |

### [Sample 4]

> **Text:** In the above context, learned counsel for State sought to rely on the legal presumption envisaged in Section 35 of the Act,

| Token | Content | Error Type | Details |
| --- | --- | --- | --- |
| 19 | `Section` | **False Negative** | Predicted=False, Truth=True |
| 20 | `35` | **False Negative** | Predicted=False, Truth=True |

### [Sample 5]

> **Text:** It did not expressly refer to the acts of an `agent'' other than an election agent and thus created some difficulty as Sub-section (1) was subject to the provisions of Sub-section (2) which dealt only with corrupt practices committed by `agents'' other than election agents.

| Token | Content | Error Type | Details |
| --- | --- | --- | --- |
| 25 | `Sub-section` | **False Negative** | Predicted=False, Truth=True |
| 26 | `(` | **False Negative** | Predicted=False, Truth=True |
| 27 | `1` | **False Negative** | Predicted=False, Truth=True |
| 28 | `)` | **False Negative** | Predicted=False, Truth=True |
| 35 | `Sub-section` | **False Negative** | Predicted=False, Truth=True |
| 36 | `(` | **False Negative** | Predicted=False, Truth=True |
| 38 | `)` | **False Negative** | Predicted=False, Truth=True |
| 54 | `.` | **False Positive** | Predicted=True, Truth=False |

---

## 📊 Summary Statistics

| Metric | Value |
| --- | --- |
| **Model** | `gemma3:12b` |
| **Sample Count** | 10 |
| **Total Tokens** | 357 |
| **Precision** | 0.4000 |
| **Recall** | 0.1500 |
| **F1 Score** | 0.2182 |

**Performance Timing:**

* **Total Execution Time:** 159.12s
* **Average Time per Text:** 15.91s

---

Would you like me to help you analyze why the model is struggling with these specific legal citations and punctuation marks?