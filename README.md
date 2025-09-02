# 💸 Money Laundering Detection  

## 👋 About the Project  
This is my project on detecting **money laundering activities** using **machine learning**.  
The dataset contains both **normal transactions** and **suspicious ones**, which made it interesting because the data was **imbalanced** (very few laundering cases compared to normal ones).  

The idea is based on the **money laundering cycle**:  
- **Placement** → putting illegal money into the system  
- **Layering** → making complex transfers to hide the source  
- **Integration** → making the money look legal again  

My goal was to apply **data analysis and ML models** to figure out which transactions might be suspicious.  

---

## 🎯 Objectives  
- Handle the **imbalanced dataset** problem.  
- Train and compare different ML models.  
- Focus on **precision and recall** (catching laundering is more important than just accuracy).  
- Learn and apply preprocessing steps like scaling, encoding, and undersampling.  

---

## 📂 Dataset  
I used IBM’s synthetic financial transaction dataset (from Kaggle).  

- **HI-Large_Trans.csv** → training (more laundering cases).  
- **LI-Large_Trans.csv** → testing (fewer laundering cases).  

**Important Columns:**  
- `Timestamp` → when the transaction happened  
- `Amount Paid` / `Amount Received`  
- `Payment Format` → ACH, Bitcoin, Credit Card, etc.  
- `Payment Currency` / `Receiving Currency`  
- `Is Laundering` → target variable (0 = genuine, 1 = laundering)  

---

## 🛠️ Preprocessing Steps  
- **Undersampling** → to balance laundering vs. non-laundering cases  
- **Feature Engineering** → created new time-based features from timestamp  
- **Encoding** → converted categorical features into numerical form  
- **Scaling** → applied RobustScaler to handle outliers in amounts  

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
- **Imbalanced datasets are challenging** → undersampling was essential.  
- Outliers in transaction amounts gave important clues for laundering detection.  
- **Random Forest and XGBoost** worked the best for this problem.  
- In fraud detection, **recall matters more than accuracy** because missing a laundering case is riskier than a false alarm.  

---


