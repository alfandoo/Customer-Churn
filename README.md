# 📉 Customer Churn Prediction  
## Machine Learning for Customer Retention

---

# 📌 Project Overview

Proyek *Customer Churn Prediction* ini dibangun untuk membantu bisnis dalam memahami dan memprediksi pelanggan yang berpotensi berhenti berlangganan (*churn*). Dengan model ini, tim Customer Success atau Marketing dapat mengambil aksi proaktif untuk menurunkan churn dan mempertahankan pelanggan bernilai tinggi.

---

# 🎯 Business Problem

Churn—ketika pelanggan berhenti memakai layanan—dapat merugikan bisnis karena:

- Berdampak langsung pada revenue
- Meningkatkan CAC (Customer Acquisition Cost)
- Mengurangi lifetime value
- Mendorong kompetisi di pasar

Tujuan utama proyek ini:

1. Memprediksi churn pelanggan secara akurat
2. Mengidentifikasi faktor churn utama
3. Memberikan rekomendasi retention berbasis data

---

# 📂 Dataset Overview

Dataset berisi data pelanggan dengan atribut seperti:

- Demografi
- Account & service usage
- Biaya & pembayaran
- Gender, tenure, contract type
- Feature churn status (Yes/No)

Target: `Churn` (binary).

Dataset ini umum ditemukan pada use case *telecom / subscription business*.

---

# 🧪 Methodology (CRISP-DM)

## 1️⃣ Business Understanding

Memahami dampak churn terhadap revenue dan strategi retensi yang dapat dilakukan.

## 2️⃣ Data Understanding

Initial EDA mencakup:

- Distribusi target churn vs non-churn
- Analisis outlier
- Korelasi antar fitur
- Identifikasi missing values

## 3️⃣ Data Preparation

Langkah preprocessing:

- Encoding kategori (Label/One-Hot)
- Feature scaling
- Handling missing values
- Train/test split
- Penanganan class imbalance

---

# 📊 Modeling

Model yang dievaluasi:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Random Forest
- Support Vector Machine (SVM)
- Gradient Boosting

Evaluation metrics:

- Accuracy
- F1 Score
- ROC-AUC
- Confusion Matrix

---

# 📈 Model Performance

| Model | Accuracy | F1 Score | ROC-AUC |
|--------|----------|----------|---------|
| Random Forest | 0.802 | 0.684 | 0.782 |
| Logistic Regression | 0.791 | 0.678 | 0.802 |
| SVM | 0.794 | 0.687 | 0.768 |
| Gradient Boosting | 0.815 | 0.702 | 0.805 |
| KNN | 0.761 | 0.612 | 0.743 |

> *Metrics di atas adalah contoh; harap sesuaikan dengan hasil aktual dari run Anda.*

---

# 🔎 Feature Importance (Random Forest)

Contoh top 10 fitur penting:

| Feature | Importance |
|---------|------------|
| Tenure | 0.217 |
| MonthlyCharges | 0.184 |
| Contract | 0.156 |
| InternetService | 0.109 |
| SeniorCitizen | 0.072 |
| PaymentMethod | 0.055 |
| TotalCharges | 0.044 |
| OnlineSecurity | 0.029 |
| TechSupport | 0.024 |
| OnlineBackup | 0.020 |

> *Fitur importance dapat bervariasi tergantung model.*

Insight:
- Lama berlangganan (*Tenure*) adalah indikator churn terkuat.
- Biaya bulanan dan tipe kontrak berkorelasi kuat dengan churn.

---

# 🧠 Key Insights

## 💡 1. Customer Tenure

Pelanggan dengan usia kontrak pendek cenderung churn lebih tinggi → kemungkinan kurangnya keterikatan.

## 💡 2. Billing & Payment

Fitur seperti *MonthlyCharges* & *PaymentMethod* menunjukkan pengaruh kuat terhadap churn → impak biaya terhadap retensi.

## 💡 3. Service Usage

Layanan seperti *InternetService*, *TechSupport*, *OnlineSecurity* memberikan sinyal churn behavior.

---

# 🚀 Business Recommendations

### 💼 Retention Strategy

1. **Loyalty Rewards Program**  
   Tawarkan benefit untuk pelanggan dengan tenure rendah untuk meningkatkan retensi.

2. **Contract Incentives**  
   Diskon atau insentif untuk long-term contracts.

3. **Churn Alert System**  
   Implementasi model sebagai *churn early warning system* yang memicu action tim Customer Success.

---

### 🤝 Customer Experience

1. **Feedback Loop**  
   Survey pelanggan dengan risiko churn tinggi untuk memahami pain points.

2. **Tingkatkan Layanan Dukungan**  
   Fokus pada fitur support yang menjadi faktor churn (misal: TechSupport, OnlineSecurity).

3. **Optimalisasi Billing Transparency**  
   Komunikasikan biaya dengan lebih jelas untuk mengurangi churn karena billing issues.

---

