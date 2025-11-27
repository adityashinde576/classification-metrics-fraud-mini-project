Mini Project – Classification Metrics (Fraud Detection)
📌 1. Overview

This mini project demonstrates how to evaluate a binary classification model using key metrics:

Accuracy

Precision

Recall

F1-Score

Confusion Matrix

We use a simple fraud detection dataset where:

1 = Fraud

0 = Normal Transaction

📌 2. Dataset
y_true = [1, 0, 1, 1, 0, 1, 0, 0, 1, 0]   # Actual labels
y_pred = [1, 0, 0, 1, 0, 1, 1, 0, 1, 0]   # Model predictions

📌 3. Confusion Matrix
Actual \ Predicted	0	1
0 (Normal)	TN	FP
1 (Fraud)	FN	TP

Definitions:

TP – Model predicted fraud & it was fraud

TN – Model predicted normal & it was normal

FP – Model predicted fraud but it was normal (False Alarm)

FN – Model predicted normal but it was fraud (Missed Fraud)

📌 4. Metric Formulas 

These formulas use plain text so they work on GitHub:

Accuracy = (TP + TN) / (TP + TN + FP + FN)

Precision = TP / (TP + FP)

Recall = TP / (TP + FN)

F1 Score = 2 * (Precision * Recall) / (Precision + Recall)

📌 5. Python Code (metrics_check.py)
from sklearn.metrics import (
    confusion_matrix,
    accuracy_score,
    precision_score,
    recall_score,
    f1_score
)

# Dataset
y_true = [1, 0, 1, 1, 0, 1, 0, 0, 1, 0]
y_pred = [1, 0, 0, 1, 0, 1, 1, 0, 1, 0]

# Compute Metrics
conf_matrix = confusion_matrix(y_true, y_pred)
accuracy = accuracy_score(y_true, y_pred)
precision = precision_score(y_true, y_pred)
recall = recall_score(y_true, y_pred)
f1 = f1_score(y_true, y_pred)

# Print Results
print("Confusion Matrix:\n", conf_matrix)
print(f"Accuracy  : {accuracy:.4f}")
print(f"Precision : {precision:.4f}")
print(f"Recall    : {recall:.4f}")
print(f"F1 Score  : {f1:.4f}")

📌 6. Interpretation (Fraud Detection Context)

Accuracy → overall correctness

Precision → when model says “fraud”, how often it is correct

Recall → how many real frauds the model detects

F1 score → balanced measure of precision and recall

⚠ In Banking:

High FN (missed fraud) = big financial loss

High FP (false fraud alerts) = angry customers

Fraud models should prioritize Recall.

📌 7. How to Run
Install dependencies
pip install scikit-learn

Run the script
python metrics_check.py
