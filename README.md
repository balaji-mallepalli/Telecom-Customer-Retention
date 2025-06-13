# 📞 Telecom Customer Retention

## 📌 Objective
To build a predictive machine learning model that can accurately identify customers who are likely to churn from a telecom service provider, enabling proactive customer retention strategies.

---

## 🗂️ Table of Contents
- [Objective](#objective)
- [Dataset](#dataset)
- [Technologies Used](#technologies-used)
- [Data Preprocessing](#data-preprocessing)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Modeling](#modeling)
- [Evaluation Metrics](#evaluation-metrics)
- [Key Insights](#key-insights)
- [Conclusion](#conclusion)
- [Project Structure](#project-structure)
---

## 📊 Dataset
- **Name:** Telecom Customer Churn Dataset  
- **Size:** 7,043 records × 21 columns  
- **Target Column:** `Churn` (binary: Yes → 1, No → 0)  
- **Source:** Kaggle

---

## 🧰 Technologies Used
- **Language:** Python  
- **Environment:** Google Colab  
- **Libraries:**
  - `pandas`, `numpy` – Data processing
  - `matplotlib`, `seaborn`, `missingno` – Visualization
  - `scikit-learn`, `xgboost` – Modeling and evaluation

---

## 🧹 Data Preprocessing
- Converted all categorical columns to numerical using `.replace()`.
- Handled null values in `TotalCharges` (set to 0 for zero-tenure customers).
- Dropped `customerID` (irrelevant for modeling).
- Removed `TotalCharges` to avoid multicollinearity with `MonthlyCharges`.

---

## 📊 Exploratory Data Analysis
- Visualized churn distribution (~26.5% churn rate).
- Analyzed feature impact using:
  - Correlation heatmap
  - Count plots (e.g., `InternetService`, `TechSupport`, `tenure`)
- Found patterns like:
  - Low tenure customers more likely to churn.
  - Paperless billing and electronic check payment methods correlated with higher churn.

---

## 🤖 Modeling
Used `XGBoostClassifier` with the following key settings:
- `learning_rate=0.1`
- `n_estimators=1000` (with early stopping)
- `max_depth=5`, `subsample=0.8`, `colsample_bytree=0.8`

Split:
- 70% Training, 30% Testing

---

## 📈 Evaluation Metrics
| Metric         | Value     |
|----------------|-----------|
| Accuracy       | **80.55%** |
| AUC Score      | **0.849**  |

---

## 🔍 Key Feature Importances
- `MonthlyCharges`
- `tenure`
- `PaymentMethod`
- `Contract`
- `InternetService`

---

## ✅ Conclusion
The model effectively predicts customer churn with a high AUC score. This solution can help telecom companies:
- Identify at-risk customers.
- Offer tailored promotions.
- Improve customer retention strategies.

---

## 📁 Project Structure
```bash
Telecom-Customer-Retention/
├── Telecom_Customer_Retention.ipynb               # Main Colab notebook
├── Telecom_Customer_Retention.ipynb - Colab.pdf   # Exported PDF
├── Telecom-Customer-Retention.pptx                # Presentation slides
└── telecom churn.csv                              # Dataset
└── README.md                                      # Project overview
