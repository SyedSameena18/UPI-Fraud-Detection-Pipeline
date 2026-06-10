## 📖 Important Project Keywords & Domain Definitions

---

### 🛠️ PHASE 1: DATA PREPROCESSING AND IMBALANCE HANDLING

#### 1. Data Preprocessing
* **Definition:** The process of scrubbing, filtering, and preparing raw, messy data so that machine learning models can read it without crashing.
* **In Our Project:** > Removed useless text columns like UPI account names and filtered out low-risk everyday merchant payments to keep the data fast and clean.

#### 2. Feature Engineering / Encoding
* **Definition:** Converting non-numeric data (like text words) into numbers, because computer algorithms can only calculate mathematical equations.
* **In Our Project:** > Used `LabelEncoder` to change text categories like `TRANSFER` and `CASH_OUT` into binary numbers like `0` and `1`.

#### 3. Class Imbalance
* **Definition:** A problem where one category in a dataset completely overpowers the other category, making the data highly unfair for training.
* **In Our Project:** > We had over 2.2 million safe transactions but only 6,570 fraud cases. The data was heavily skewed toward safe transfers, making standard models highly biased.

#### 4. SMOTE (Synthetic Minority Over-sampling Technique)
* **Definition:** A smart algorithm that fixes data imbalance by creating brand-new, realistic examples of the rare category based on real mathematical patterns.
* **In Our Project:** > Instead of just copying the same old fraud rows, SMOTE generated realistic synthetic fraud records to give us a perfect 50-50 balanced training dataset.

---

### 📊 PHASE 2: TABULAR MODELING VIA STACKED ENSEMBLE ML

#### 1. Ensemble Learning
* **Definition:** A method where you combine the predictions of multiple machine learning models (multiple "brains") to make one final, highly accurate decision.
* **In Our Project:** > Instead of relying on just one algorithm, we used Random Forest and XGBoost together in a stacked formation.

#### 2. Random Forest Classifier
* **Definition:** An algorithm that creates dozens of independent "Decision Trees" (like a forest of guessing games) and takes the majority vote to find the final answer.
* **In Our Project:** > It acted as our highly stable baseline model, giving **67% Precision** and minimizing false alarms for innocent customers.

#### 3. XGBoost (Extreme Gradient Boosting)
* **Definition:** A powerful, lightning-fast algorithm that builds decision trees sequentially, where each new tree specifically focuses on fixing the classification mistakes made by the previous ones.
* **In Our Project:** > It acted as our ultimate security shield, catching a near-perfect **99% of all fraud cases**.

#### 4. Precision vs. Recall
* **Precision:** Out of all the times the AI rings the fraud alarm, how many times was it actually a real scammer? *(Higher means fewer false alarms for normal users)*.
* **Recall:** Out of all the actual scammers hidden in the bank, what percentage did the AI successfully catch? *(Higher means maximum safety against asset theft)*.
* **In Our Project:** > XGBoost delivered an incredible **99% Recall**, meaning it successfully intercepted almost every single thief.

---

### 🌐 PHASE 3: RELATIONAL TOPOLOGY VIA GRAPH NEURAL NETWORKS (GNNs)

#### 1. Relational Topology
* **Definition:** It is the study of how data points are connected and arranged structurally within a network, rather than looking at them as isolated individual rows in an Excel sheet.
* **In Our Project:** > Instead of evaluating a single UPI transaction completely by itself, we map the entire relational web to track how money moves across multiple deep bank accounts.

#### 2. Graph Neural Networks (GNNs)
* **Definition:** A type of Artificial Intelligence (AI) specifically built to process, analyze, and learn from data that is structured natively as a network or a graph.
* **In Our Project:** > Standard machine learning (like XGBoost) only evaluates transaction weights and timestamps. A GNN captures the structural shapes of the connections to expose complex money laundering loops where money hops through 5 or 6 target layer accounts.

#### 3. Node (Vertex)
* **Definition:** A single discrete point, object, or entity inside a network map structure.
* **In Our Project:** > Every unique UPI Bank Account ID (`nameOrig` and `nameDest`) serves as an independent node in our topology graph.

#### 4. Edge (Link)
* **Definition:** The line, connection, or link that physically bridges two nodes together, representing a real relationship or transaction event between them.
* **In Our Project:** > Every single UPI transaction transfer acts as a directed edge connecting the respective sender node to the receiver node.

#### 5. Directed Graph (DiGraph)
* **Definition:** A network graph topology where connections are asymmetric and have a specific directional vector pointing from one node directly to another.
* **In Our Project:** > Financial funds always travel in an explicit direction (from Sender $\rightarrow$ to Receiver). Because capturing the directional path is critical for tracking velocity and financial leakages, our topology is built as a Directed Graph.
