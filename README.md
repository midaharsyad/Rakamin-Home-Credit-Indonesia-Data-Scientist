# 📊 Credit Risk Prediction Model

## 📌 Project Overview
Project ini bertujuan membangun model machine learning untuk memprediksi risiko gagal bayar nasabah berdasarkan data profil, finansial, dan riwayat kredit. Model ini dapat membantu institusi keuangan dalam mengambil keputusan pemberian pinjaman secara lebih akurat dan berbasis data.

---

## 🎯 Objectives
- Mengidentifikasi nasabah berisiko tinggi gagal bayar
- Membandingkan performa beberapa algoritma machine learning
- Menentukan model terbaik berdasarkan metrik evaluasi
- Memberikan insight bisnis berbasis hasil analisis model

---

## 📂 Dataset
Dataset berisi informasi karakteristik nasabah seperti:
- Income type
- Education level
- Employment status
- Ownership (mobil & rumah)
- Riwayat kredit
- Phone change history
- Dan variabel finansial lainnya

---

## ⚙️ Modeling Approach
Beberapa model yang diuji:
- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- Extra Trees

Model dievaluasi menggunakan:
- Accuracy
- Precision
- Recall
- F1 Score
- ROC AUC
- Confusion Matrix

---

## 🏆 Best Model Result
Model terbaik: XGBoost

Alasan pemilihan:
- ROC AUC tertinggi
- Recall class risiko tinggi lebih baik
- Keseimbangan performa antar metrik

---

## 📊 Key Insights
- Faktor pendidikan dan income type sangat memengaruhi risiko kredit
- Status pekerjaan stabil menurunkan risiko gagal bayar
- Riwayat perubahan nomor HP berkorelasi dengan tingkat risiko

---

## 💡 Business Recommendations
- Menggunakan model sebagai alat credit scoring utama untuk menyaring pengajuan kredit beresiko tinggi
- Menerapkan Behavior Scoring berbasis pola perilaku nasabah untuk meningkatkan akurasi penilaian risiko
- Melakukan segmentasi berdasarkan profil risiko untuk menyesuaika strategi misalnya penentuan tenor, limit, atau bunga sesuai tingkat risiko masing-masing segmen
- Menerapkan kebijakan risk-based pricing agar nasabah berisiko tinggi dikenakan syarat lebih ketat, sementara nasabah stabil mendapat benefit lebih baik
- Melakukan monitoring berkala dan retraining model agar performa tetap optimal seiring perubahan data dan perilaku nasabah

---

## 🛠️ Tools & Libraries
- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn

---

## 📎 How to Run
1. Clone repository
2. Install dependencies
3. Jalankan notebook
4. Pastikan dataset tersedia pada path yang sesuai

---

## 👩‍💻 Author
Project by: Khamidah Arsyad Daud
Machine Learning & Data Analysis Enthusiast