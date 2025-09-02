# 💸 Money Laundering Detection  

## 👋 About the Project  
This is my project on detecting **money laundering activities** using **machine learning**.  
The dataset contains both **normal transactions** and **suspicious ones**, which made it interesting because the data was **imbalanced** (very few laundering cases compared to normal ones).  

### 🌍 What is Money Laundering?  
Money laundering is the process of disguising illegally obtained money to make it appear legitimate.  
It usually happens in **3 stages**:  
- **Placement** → putting illegal money into the system  
- **Layering** → moving money through complex transfers to hide its source  
- **Integration** → reintroducing the cleaned money into the economy as “legal” funds  

By analyzing transaction patterns, we can try to catch laundering attempts hidden among legitimate activities.  

---

## 🎯 Objectives  
- Handle the **imbalanced dataset** problem.  
- Train and compare different ML models.  
- Focus on **precision and recall** (catching laundering is more important than raw accuracy).  
- Learn and apply preprocessing steps like scaling, encoding, and undersampling.  

---

## 📂 Dataset  
I used **IBM’s synthetic financial transaction dataset** (available on Kaggle).  

- **HI-Large_Trans.csv** → training (higher % of laundering cases).  
- **LI-Large_Trans.csv** → testing (lower % of laundering cases).  

**Key Features:**  
- `Timestamp` → when the transaction happened  
- `Amount Paid` / `Amount Received`  
- `Payment Format` → ACH, Bitcoin, Credit Card, etc.  
- `Payment Currency` / `Receiving Currency`  
- `Is Laundering` → target variable (0 = genuine, 1 = laundering)  

---

## 🛠️ Preprocessing Steps  
- **Undersampling** → balance between laundering & non-laundering cases  
- **Feature Engineering** → extracted time-based features (year, month, hour, etc.)  
- **Encoding** → categorical variables converted into numerical form  
- **Scaling** → used RobustScaler to reduce effect of outliers in transaction amounts  

---

## 🤖 Models Used  

| Model                  | Precision | Recall | F1-Score | Accuracy |
|-------------------------|-----------|--------|----------|----------|
| Logistic Regression     | 0.87      | 0.88   | 0.88     | 0.88     |
| Random Forest           | 0.95      | 0.84   | 0.89     | 0.90     |
| XGBoost                 | 0.93      | 0.86   | 0.90     | 0.90     |
| Stacking Classifier     | 0.92      | 0.87   | 0.89     | 0.89     |

✨ **Best Models:** Random Forest & XGBoost (both ~90% accuracy).  

---

## 📊 Test Results (LI-Large_Trans.csv)  

| Model         | Precision | Recall | F1-Score | Accuracy | ROC AUC |
|---------------|-----------|--------|----------|----------|---------|
| Random Forest | 0.91      | 0.92   | 0.87     | 0.87     | 0.8687  |
| XGBoost       | 0.91      | 0.92   | 0.88     | 0.88     | 0.8687  |

---

## ✅ Key Learnings  
- **Imbalanced datasets are tricky** → undersampling really helped.  
- Outliers in `Amount Paid` and `Amount Received` were strong laundering indicators.  
- **Random Forest and XGBoost** turned out to be the most reliable models.  
- In fraud detection, **recall > accuracy** → better to raise a false alarm than to miss an actual laundering case.  

---

## 🚀 Future Work  
- Try **SMOTE or advanced hybrid sampling** instead of plain undersampling.  
- Experiment with **deep learning models (LSTM/Autoencoders)** for sequential data.  
- Deploy the model as a **web app or API** for real-time transaction monitoring.  

---

## 👨‍💻 Author  
This project is part of my ML journey, where I’m exploring how **AI can help fight financial crimes**.  
The goal is to bridge the gap between **finance, security, and machine learning** 🚀.  
