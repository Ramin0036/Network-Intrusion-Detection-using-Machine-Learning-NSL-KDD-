# Network Intrusion Detection using Machine-Learning (NSL-KDD)

## 📌 Project Overview

This project implements an **Anomaly-Based Intrusion Detection System (IDS)** using the **One-Class Support Vector Machine (One-Class SVM)** algorithm on the **NSL-KDD** dataset.

Unlike traditional supervised classification methods, One-Class SVM is trained **only on normal network traffic** and learns the boundary of legitimate behavior. During testing, any traffic sample that falls outside this learned boundary is considered an anomaly or potential cyber attack.

---

## 🎯 Problem Statement

Cyber attacks are becoming increasingly sophisticated, making it difficult to detect unknown attacks using traditional signature-based systems.

The objective of this project is to:

- Detect abnormal network traffic using anomaly detection.
- Train the model using only normal network connections.
- Identify unknown attacks as outliers.
- Evaluate the effectiveness of One-Class SVM for intrusion detection on the NSL-KDD benchmark dataset.

---

## 📂 Dataset

This project uses the **NSL-KDD** dataset, an improved version of the KDD Cup 1999 dataset designed to remove redundant records and provide a better benchmark for intrusion detection research.

### Download Dataset

Official GitHub Repository:

https://github.com/jmnwong/NSL-KDD-Dataset

Alternative Source:

https://www.unb.ca/cic/datasets/nsl.html

Dataset files include:

- KDDTrain+.txt
- KDDTest+.txt
- KDDTrain+_20Percent.txt
- KDDTest-21.txt

---

## 🧠 Methodology

This project follows an anomaly detection approach using the **One-Class Support Vector Machine (One-Class SVM)** algorithm.

Unlike traditional supervised learning methods, the model is **trained exclusively on normal network traffic**. During the training phase, the algorithm learns the decision boundary that represents legitimate network behavior.

After training, the model is evaluated using a **mixed test dataset containing both normal and attack traffic**. Any sample that falls outside the learned boundary is classified as an anomaly and is considered a potential intrusion or cyber attack.

The workflow of the project is as follows:

1. Load the NSL-KDD dataset.
2. Perform data preprocessing and feature engineering.
3. Encode categorical features.
4. Normalize numerical features.
5. Select only **normal traffic** for model training.
6. Train the **One-Class SVM** model.
7. Test the model using a dataset containing **both normal and attack samples**.
8. Evaluate the model using Accuracy, Precision, Recall, F1-Score, and Confusion Matrix.

---

## 🤖 Algorithm

**One-Class Support Vector Machine (One-Class SVM)**

One-Class SVM is an unsupervised anomaly detection algorithm that learns the distribution of normal data.

Training data:

- Normal Traffic ✅

Testing data:

- Normal Traffic
- Attack Traffic

Prediction:

- +1 → Normal
- -1 → Anomaly (Attack)

---

## 📊 Features

- Data preprocessing
- Label encoding
- Feature normalization
- One-Class SVM training
- Intrusion detection
- Confusion Matrix
- Accuracy
- Precision
- Recall
- F1-score

---

## ⚙️ Requirements

```bash
pip install pandas
pip install numpy
pip install scikit-learn
pip install matplotlib
pip install seaborn
```

---

## 🚀 Run

open

Project.ipynb

and run all cells.

---

## 📈 Evaluation Metrics

The model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

---

## 💡 Why One-Class SVM?

One-Class SVM is particularly suitable for intrusion detection because:

- It requires only normal traffic for training.
- It can detect previously unseen attacks.
- It performs anomaly detection without requiring balanced datasets.
- It is widely used in cybersecurity research.

---
---

# 📈 Results

The performance of the proposed One-Class SVM model was evaluated using standard classification metrics.

## Initial Model Performance

The initial implementation of the One-Class SVM produced the following results:

| Class | Precision | Recall | F1-Score | Support |
|--------|----------:|-------:|---------:|--------:|
| Attack (-1) | 0.00 | 0.00 | 0.00 | 3119 |
| Normal (1) | 0.94 | 1.00 | 0.97 | 48881 |

**Overall Accuracy:** **94%**

> The initial model failed to detect attack samples because the decision boundary was too conservative. This motivated further preprocessing and parameter tuning.

---

## Final Model Performance

After preprocessing and model optimization, the final One-Class SVM achieved the following performance:

| Class | Precision | Recall | F1-Score | Support |
|--------|----------:|-------:|---------:|--------:|
| Attack (-1) | 0.94 | 0.93 | 0.94 | 26062 |
| Normal (1) | 0.93 | 0.95 | 0.94 | 25938 |

### Overall Performance

| Metric | Value |
|---------|-------|
| Accuracy | **94%** |
| Macro Precision | **94%** |
| Macro Recall | **94%** |
| Macro F1-Score | **94%** |
| Weighted F1-Score | **94%** |

---

## 📌 Summary

The optimized One-Class SVM successfully learned the distribution of normal network traffic and achieved approximately **94% accuracy** on the NSL-KDD dataset.

The model demonstrated balanced performance for both normal and attack traffic, making it a suitable anomaly detection approach for network intrusion detection systems.

---

## 👨‍💻 Author

**Ramin Allahverdizadeh**

Network Intrusion Detection using One-Class SVM

GitHub: https://github.com/Ramin0036
