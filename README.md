# An Intelligent UPI Fraud Detection System Using Stacked Machine Learning and Graph Neural Networks

---

## 📌 Project Overview
In modern digital payment infrastructures, financial fraud is a multi-crore problem characterized by extreme data scarcity. This project builds a production-grade, end-to-end data pipeline designed to detect fraudulent UPI transactions in real time. 

By analyzing **6.3 million transactions**, this system mitigates extreme class imbalance to train a high-sensitivity hybrid system. It combines tabular machine learning classifiers with structural relational modeling to act as an immediate shield against digital asset theft.

---

## 🚫 The Existing System (The Limitation)
Most traditional banking security systems rely on rigid, rule-based algorithms (e.g., *"Flag transaction if amount > ₹5,00,000"*). 

### Major Flaws in Existing Systems:
* **High Vulnerability:** Modern scammers constantly alter their transaction patterns, easily bypassing static rules.
* **The "Lazy AI" Problem (Class Imbalance):** Because actual fraud accounts for less than **0.13%** of real-world financial data, standard Machine Learning models suffer from high bias. They simply guess "Safe" every single time, achieving 99.9% accuracy on paper while completely failing to catch actual thieves.
* **Lack of Relationship Tracking:** Standard tabular systems analyze transactions individually. They completely miss the structural connections, such as a single scammer account rapidly distributing money to multiple temporary bank accounts.

---

## 💡 The Proposed System (Our Multi-Model Solution)
Our project introduces an optimized, intelligence-driven data pipeline that processes massive transaction streams using a multi-layered approach to catch both pattern-based and network-based fraud.

### How We Solved It (Phase-by-Phase Architecture):
1. **Data Preprocessing & Imbalance Handling (My Core Contribution):** Filtered out low-risk merchant data to isolate `TRANSFER` and `CASH_OUT` streams where 99% of digital payment scams actually occur. To fix the 0.13% fraud scarcity, I implemented **SMOTE (Synthetic Minority Over-sampling Technique)**, generating realistic synthetic records to balance the training set to a perfect **50-50 ratio**.
2. **Tabular Modeling via Stacked Ensemble ML:** Trained two high-performance tabular "brains" on the balanced data. **Random Forest** provides high stability with a low false-alarm rate (**67% Precision**), while **XGBoost** acts as an aggressive fraud catcher, achieving a near-perfect **99% Recall rate**.
3. **Relational Topology via Graph Neural Networks (GNNs):** Map the transactions into a visual graph network where bank accounts are "nodes" and money transfers are "edges." This allows the system to trace complex money laundering paths.
4. **API Integration & Interactive Dashboarding:** Connects the entire backend pipeline to a real-time Streamlit dashboard interface for easy security monitoring.

---

## 🎛️ Tech Stack & Professional Tools

| Layer | Technology / Tool | Business Use Case |
| :--- | :--- | :--- |
| **Language** | Python 3.x | Core algorithmic development & scripting |
| **Data Engineering** | Pandas, NumPy | High-performance cleaning & processing of 6.3M rows |
| **Imbalance Mitigation** | Imbalanced-Learn (`SMOTE`) | Synthetic data generation to eliminate model bias |
| **Tabular Ensembling** | XGBoost, Random Forest | High-sensitivity stacked machine learning classifiers |
| **Graph Intelligence** | PyTorch Geometric / NetworkX | Building structural GNNs to catch relational network fraud |
| **User Interface** | Streamlit | Developing the live analytics dashboard screen |

---

## 📈 Key Metrics & Business Impact
Performance metrics matter, This pipeline delivers enterprise-grade results on hidden validation data:

* **XGBoost Recall: 99%** — Successfully intercepts 99% of all fraudulent attempts before they clear.
* **Random Forest Precision: 67%** — Keeps false alarms low, protecting the customer experience for innocent users.
* **Data Scale:** Optimized from a raw 6.3-million-row wall into a clean, balanced, 7-dimensional training matrix.

---


