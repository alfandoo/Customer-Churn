# 📉 Telco Customer Churn Prediction  
## End-to-End Machine Learning Project (CRISP-DM)

---

# 📌 Project Overview

Proyek ini bertujuan untuk memprediksi pelanggan yang berpotensi churn pada industri telekomunikasi menggunakan dataset **Telco Customer Churn (Kaggle)**.

Customer churn merupakan salah satu tantangan utama bisnis subscription karena berdampak langsung terhadap:

- Revenue loss
- Customer Acquisition Cost (CAC)
- Customer Lifetime Value (CLV)
- Market competitiveness

Model ini dirancang sebagai **early warning system** untuk membantu tim bisnis melakukan intervensi sebelum pelanggan benar-benar berhenti berlangganan.

---

# 🎯 Business Problem

Bagaimana mengidentifikasi pelanggan yang memiliki risiko tinggi churn sehingga perusahaan dapat:

1. Menurunkan churn rate
2. Meningkatkan customer retention
3. Mengoptimalkan strategi pricing & kontrak
4. Meningkatkan lifetime value pelanggan

---

# 📂 Dataset

- Source: Kaggle – Telco Customer Churn
- Total records: ~7.000 pelanggan
- Target: `Churn` (Yes/No)

Fitur utama mencakup:

- Tenure (lama berlangganan)
- MonthlyCharges & TotalCharges
- Contract type
- Internet service
- Payment method
- Tech support & add-on services
- Demografi (SeniorCitizen, Dependents, dll)

Dataset memiliki class imbalance (churn sekitar 26–27%).

---

# 🧪 Methodology (CRISP-DM)

## 1️⃣ Business Understanding
Mendefinisikan churn sebagai problem klasifikasi biner untuk mendukung strategi retensi.

## 2️⃣ Data Understanding
- Distribusi churn vs non-churn
- Analisis korelasi
- EDA per fitur numerik & kategorikal
- Identifikasi imbalance class

## 3️⃣ Data Preparation
- One-Hot Encoding untuk fitur kategorikal
- Scaling untuk fitur numerik
- Train-test split
- Pipeline + GridSearchCV
- Evaluasi menggunakan multiple metrics

## 4️⃣ Modeling

Model yang diuji:

- Logistic Regression
- Random Forest
- XGBoost
- Support Vector Machine (SVC)
- K-Nearest Neighbors (KNN)

---

# 📊 Model Performance (Test Set)

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC | AP |
|--------|----------|-----------|--------|------|---------|------|
| Logistic Regression | 0.752 | 0.522 | **0.774** | **0.623** | **0.845** | **0.640** |
| Random Forest | 0.760 | 0.533 | 0.749 | 0.623 | 0.840 | 0.622 |
| XGBoost | **0.772** | **0.555** | 0.706 | 0.622 | 0.843 | 0.638 |
| SVC | 0.762 | 0.536 | 0.739 | 0.621 | 0.832 | 0.622 |
| KNN | 0.713 | 0.475 | 0.803 | 0.597 | 0.810 | 0.533 |

---

# 🏆 Best Model

### Logistic Regression (Based on F1 Score)

Walaupun XGBoost memiliki accuracy tertinggi, Logistic Regression dipilih sebagai best model karena:

- F1 Score tertinggi (0.623)
- ROC-AUC tertinggi (0.845)
- Recall tinggi (0.774) → penting untuk menangkap churner
- Lebih interpretable untuk kebutuhan bisnis

Best Parameters:
```
{'classifier__C': 1, 'classifier__solver': 'lbfgs'}
```

---

# 🔎 Key Feature Importance (Logistic Regression Coefficients)

| Feature | Effect |
|----------|--------|
| tenure | 🔻 Menurunkan churn |
| TotalCharges | 🔺 Meningkatkan churn |
| Contract_Two year | 🔻 Sangat menurunkan churn |
| Contract_Month-to-month | 🔺 Meningkatkan churn |
| InternetService_DSL | 🔻 |
| PaymentMethod_Electronic check | 🔺 |
| TechSupport_Yes | 🔻 |
| PaperlessBilling_No | 🔻 |
| InternetService_Fiber optic | 🔺 |

---

# 📈 Business Insights

## 🔁 1. Tenure is the Strongest Indicator
Semakin lama pelanggan berlangganan, semakin kecil kemungkinan churn.

➡ Fokus retensi pada pelanggan baru (tenure < 12 bulan).

---

## 📜 2. Contract Type Matters

- Month-to-month meningkatkan risiko churn.
- Two-year contract sangat menurunkan churn.

➡ Insentif untuk kontrak jangka panjang sangat efektif.

---

## 💳 3. Payment Behavior

Electronic check berkorelasi positif dengan churn.

➡ Perlu investigasi friction dalam metode pembayaran ini.

---

## 🛠 4. Support & Add-ons Reduce Churn

TechSupport dan OnlineSecurity berpengaruh menurunkan churn.

➡ Bundling layanan tambahan dapat menjadi strategi retensi.

---

# 🚀 Business Recommendations

## 1️⃣ Early Warning System
Deploy Logistic Regression model untuk scoring churn secara berkala.

## 2️⃣ Targeted Retention Campaign
- Fokus pelanggan month-to-month
- Promo upgrade ke kontrak tahunan

## 3️⃣ Pricing & Bundle Strategy
- Bundling TechSupport & Security
- Incentive untuk autopay / credit card payment

## 4️⃣ Onboarding Optimization
Program khusus untuk pelanggan baru 0–6 bulan.

---

# 🛠 Tech Stack

- Python
- Pandas & NumPy
- Scikit-learn
- XGBoost
- Matplotlib & Seaborn
- GridSearchCV Pipeline

---

# 🎯 Conclusion

Logistic Regression memberikan keseimbangan terbaik antara performa dan interpretabilitas.

Faktor utama churn:
- Tenure rendah
- Kontrak bulanan
- Electronic check
- Tidak menggunakan layanan tambahan

Model ini dapat digunakan sebagai dasar implementasi churn prediction system di industri subscription / telecom.

---

# 📎 Future Work

- Threshold tuning untuk business cost optimization
- Cost-sensitive learning
- SHAP interpretability
- Deployment via Streamlit
- Customer Lifetime Value integration
