# Behavioral-risk

# 🏦 Behavioral Risk Prediction in Banking

## 📌 Business Problem

In the banking industry, identifying high-risk customers early is critical to prevent financial losses, fraud, and poor credit decisions.
However, traditional rule-based systems often fail to capture complex behavioral patterns in customer transactions.

---

## 🎯 Project Objective

This project aims to build a **machine learning system** that predicts customer behavioral risk based on transaction and user data, enabling banks to make **data-driven risk management decisions**.

---

## 💼 Business Impact

* 🔍 Early detection of high-risk customers
* 💸 Potential reduction in financial losses due to fraud or bad credit
* ⚡ Improved efficiency in risk assessment processes
* 📊 Support for better decision-making in customer management

---

## 📂 Dataset

The project integrates multiple data sources:

* **User data** (demographics, profiles)
* **Transaction data** (spending behavior)
* **Card data**
* **MCC codes** (merchant categories)

---

## ⚙️ Methodology

### 1. Data Processing

* Data cleaning and merging from multiple sources
* Feature engineering from transaction patterns
* Train/validation/test split

### 2. Modeling

Several models were trained and compared:

* Logistic Regression
* Random Forest
* XGBoost

### 3. Model Selection

* Hyperparameter tuning applied
* Best model selected based on performance metrics

---

## 📊 Model Evaluation

### Evaluation Setup

* Dataset is imbalanced (≈ 14% positive class)
* Metrics used:

  * ROC-AUC
  * Precision / Recall
  * F1-score
* Threshold tuning applied for different business objectives

---

### 🔍 Baseline vs Advanced Models

| Model               | ROC-AUC |
| ------------------- | ------- |
| Logistic Regression | 0.8347  |
| XGBoost             | 0.8557  |
| Random Forest       | 0.8650  |

---

### ⚖️ Threshold Tuning (XGBoost Example)

| Mode       | Threshold | Precision | Recall | F1   |
| ---------- | --------- | --------- | ------ | ---- |
| Default    | 0.50      | 0.44      | 0.69   | 0.54 |
| Best F1    | 0.72      | 0.76      | 0.50   | 0.60 |
| Cost-based | 0.38      | 0.40      | 0.88   | 0.55 |

---

### 📉 Confusion Matrix (Cost-Optimized)

```text
[[131  34]
 [  3  23]]
```

* Only **3 risky customers missed (FN)**
* High recall achieved at the cost of more false positives

---

### 💼 Business Interpretation

* In risk detection:

  * **False Negatives (FN)** → very costly (missed risky customers)
  * **False Positives (FP)** → operational overhead

👉 Therefore:

* Model is tuned to **maximize recall**
* Accept higher FP to reduce risk exposure

---

### 📌 Key Insight

Model performance should not be evaluated solely on AUC.
In imbalanced risk problems, **threshold tuning and business trade-offs are critical**.

## 📁 Project Structure

```
BANKING/
│── Code Python/
│   ├── Data.ipynb
│   ├── Train.ipynb
│   ├── model files (.pkl)
│   ├── datasets (.csv)
│
│── Data/
│   ├── raw data (.xlsx)
```

---

## ▶️ How to Run

```bash
git clone https://github.com/HoangDuyQuang/Behavioral-Risk.git
cd Behavioral-Risk
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run notebooks:

* Open `Train.ipynb`
* Execute all cells

---

## 📈 Key Skills Demonstrated

* Data preprocessing & feature engineering
* Machine learning model development
* Model evaluation & tuning
* Handling real-world structured data

---

## 🔮 Future Improvements

* Deploy model as API or web app (Streamlit/FastAPI)
* Add real-time prediction pipeline
* Improve feature engineering from transaction sequences

---

## 👨‍💻 Author

**Hoang Duy Quang**

---

## ⭐ Note

This project is developed for learning and portfolio purposes in the field of Data Science and Machine Learning.
