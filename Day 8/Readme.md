#  Adversarial Fraud Detection System


##  Note

This project uses a **real-world anonymized dataset**, making it closer to actual industry fraud detection systems.

## Overview

This project focuses on building a **fraud detection system for online transactions** using a **real-world dataset** from the IEEE-CIS Fraud Detection competition.

Unlike traditional ML problems, this is an **adversarial problem**, where fraudsters continuously evolve their behavior to mimic legitimate users.

The goal is to predict the probability that a transaction is fraudulent (`isFraud = 1`) while minimizing false positives.

---

## Problem Statement

Given anonymized transaction and identity data, the task is to:

> Predict the probability of an online transaction being fraudulent.

### Key Challenges:

* Highly **imbalanced dataset** (~3.5% fraud)
* **Anonymized features** (V1–V339)
* Fraudsters mimic normal user behavior
* **Cost-sensitive problem** (false positives are expensive)

---

## Dataset Description

This project uses a **real-world dataset** released by the IEEE Computational Intelligence Society.

### Tables:

* **Transaction Table** → Transaction details (amount, card, time, etc.)
* **Identity Table** → Device & identity-related information

> Not all transactions have identity data, which itself can be a signal.

---

## Exploratory Data Analysis (EDA)

###  Key Insights:

* Fraud transactions often occur in **specific time windows (early hours)**
* Fraudsters operate within **normal transaction ranges**
* Transactions with **fewer missing values** tend to be more fraudulent
* Strong signals from **card-based and behavioral features**

---

## ⚙️ Feature Engineering

### Basic Features:

* `hour` extracted from TransactionDT
* `missing_count`, `missing_ratio`

### Behavioral Features (Planned / In Progress):

* User-level aggregation
* Velocity features (transaction frequency)
* Deviation-based features

---

## 🤖 Model

### Baseline Model:

* **LightGBM Classifier**

### Why LightGBM?

* Handles large datasets efficiently
* Works well with missing values
* Captures non-linear relationships

---

##  Feature Importance Insights

Initial model highlights:

* Card-related features (`card1`, `card2`)
* Transaction amount
* Time-based features (`TransactionDT`)
* Count and history-based features (`C`, `D` features)

---

## Key Learnings

* Fraud detection is a **behavioral problem**, not just classification
* **Velocity and user behavior** are critical signals
* Multiple features encode similar information (redundancy exists)
* Simple baseline models can reveal powerful insights

---

## Future Work

* User reconstruction (identifying same user across transactions)
* Advanced velocity features
* Target encoding with proper CV
* Model tuning and ensemble methods
* Real-time fraud scoring simulation

---

## Tech Stack

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* LightGBM

---

## Author
Zenil Ashokkumar Roy
PG Diploma IIT Gandhinagar
Built with and curiosity to understand real-world fraud behavior.
---
