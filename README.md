# 🛡️ Mini Project – Classification Metrics (Fraud Detection)

This mini project teaches how to evaluate a **binary classification model** using real fraud detection data.  
Students manually compute and interpret important ML metrics.

---

## 📌 1. Goal

The goals of this mini project are:

- Understand how classification metrics work in real-world fraud detection.
- Compute:
  - Accuracy  
  - Precision  
  - Recall  
  - F1-score  
  - Confusion Matrix
- Interpret these metrics in a banking fraud detection scenario.
- Optionally verify results using Python & sklearn.

---

## 📌 2. Problem Description

We have a binary classification problem:

- **1 = Fraud**
- **0 = Normal Transaction**

Dataset used:

- **Actual Labels (`y_true`)**  
  `[1, 0, 1, 1, 0, 1, 0, 0, 1, 0]`

- **Predicted Labels (`y_pred`)**  
  `[1, 0, 0, 1, 0, 1, 1, 0, 1, 0]`

Each index represents one transaction.

---

## 📌 3. Steps I Followed

### ✔ Step 1 — Wrote Down the Data  
Noted `y_true` and `y_pred` along with class meanings.

### ✔ Step 2 — Created Transaction Table  
Made a table:

| Index | y_true | y_pred | Type |
|-------|--------|---------|------|
| 0 | 1 | 1 | TP |
| 1 | 0 | 0 | TN |
| 2 | 1 | 0 | FN |
| ... | ... | ... | ... |

Used rules:
- **TP** = actual 1, predicted 1  
- **TN** = actual 0, predicted 0  
- **FP** = actual 0, predicted 1  
- **FN** = actual 1, predicted 0  

### ✔ Step 3 — Built Confusion Matrix

markdown
Copy code
             Predicted
          |   0   |   1   |
Actual 0 | TN | FP |
Actual 1 | FN | TP |

yaml
Copy code

Also written as:  
`[[TN, FP], [FN, TP]]`

### ✔ Step 4 — Calculated All Metrics

Using formulas:

- **Accuracy** = (TP + TN) / (TP + TN + FP + FN)
- **Precision** = TP / (TP + FP)
- **Recall** = TP / (TP + FN)
- **F1-score** = 2 * (Precision * Recall) / (Precision + Recall)

All values were calculated up to 2 decimal places.

---

## 📌 4. Interpretation (Fraud Detection Context)

- **Accuracy** tells overall correctness of the model.
- **Precision (fraud)** answers:  
  “Of all flagged frauds, how many were actually fraud?”

- **Recall (fraud)** answers:  
  “Of all real frauds, how many did we successfully detect?”

- **F1-score** balances precision and recall.

### 🏦 Fraud Detection Reality

- **False Negatives (FN)** = *missed fraud → most dangerous*  
  Banks lose money directly.

- **False Positives (FP)** = normal transactions marked as fraud  
  → annoys customers, but safer than FN.

### Final Conclusion  
(Students write their own answer)  
Example:  
> Because fraud detection is a high-risk domain, recall should be high.  
> This model needs improvement before being considered acceptable.

---

## 📌 5. Optional Python Verification (`metrics_check.py`)

If using Python, create:

from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score, confusion_matrix

y_true = [1,0,1,1,0,1,0,0,1,0]
y_pred = [1,0,0,1,0,1,1,0,1,0]

print("Accuracy:", accuracy_score(y_true, y_pred))
print("Precision:", precision_score(y_true, y_pred))
print("Recall:", recall_score(y_true, y_pred))
print("F1-Score:", f1_score(y_true, y_pred))
print("Confusion Matrix:\n", confusion_matrix(y_true, y_pred))

yaml
Copy code

Students use this to compare with manual calculations.

---

## 📌 6. Uploading to GitHub (Short Guide)

1. Create a folder:  
   `classification-metrics-fraud-mini-project`

2. Add files:
   - `README.md`
   - `metrics_check.py` (optional)

3. Go to GitHub → New Repository  
4. Upload the folder contents  
5. Commit and publish 🚀

---

## ✔ Project Completed Successfully  
This mini project teaches students to think like ML engineers — not just run code
