# 📊 Credit Risk Prediction Model

## 📌 Project Overview
Home Credit Indonesia sebagai institusi pembiayaan mengelola data aplikasi dan histori nasabah dalam jumlah besar. Tanpa analisis yang tepat, data tersebut belum dapat dimanfaatkan secara optimal untuk membedakan nasabah yang layak menerima kredit dengan yang berisiko tinggi.

Proyek ini bertujuan membangun sistem Credit Scoring berbasis Machine Learning untuk memprediksi risiko gagal bayar nasabah. Model yang dihasilkan diharapkan dapat membantu perusahaan dalam menentukan keputusan pemberian kredit, termasuk penentuan limit pinjaman dan tenor yang tepat, sehingga dapat mengurangi potensi kredit macet.

---

## 🎯 Objectives
Tujuan dari proyek ini adalah:

- Memprediksi risiko gagal bayar nasabah
- Mengidentifikasi faktor utama yang memengaruhi risiko kredit
- Mendukung proses keputusan persetujuan kredit
- Mengurangi potensi kerugian akibat kredit bermasalah
- Mengoptimalkan strategi penyaluran pinjaman berdasarkan profil risiko

---

## 📂 Dataset
Dataset utama yang digunakan adalah **application_train** yang terdiri dari:

- **307.511 baris data**
- **122 fitur**
Struktur fitur dataset:
- **103 fitur numerik** (float64 & int64)
- **19 fitur kategorikal**

Kategori informasi dalam dataset meliputi:

- **Data Demografi**  
  Usia, status keluarga, dan tingkat pendidikan.

- **Data Finansial**  
  Pendapatan, jumlah kredit yang diajukan, serta beban cicilan (annuity).

- **Riwayat Pekerjaan**  
  Jenis pekerjaan dan lama masa kerja nasabah.

---

## 🧹 Data Cleaning
Tahap pembersihan data dilakukan sebelum proses analisis dan pemodelan, meliputi:

- **Missing Value Handling**  
  Terdapat 67 kolom dengan missing value.  
  Kolom dengan missing value >65% dihapus, sedangkan kolom lainnya diimputasi menggunakan **median dan mode**.

- **Duplicate Data**  
  Tidak ditemukan data duplikat.

- **Drop Unnecessary Columns**  
  Kolom seperti `SK_ID_CURR` dan seluruh kolom `FLAG_DOCUMENT` dihapus.

- **Data Replacement**  
  Nilai seperti **XNA** dan **Unknown** diganti menggunakan nilai **modus**.
- **Outlier Handling**  
  Outlier ditangani menggunakan metode **IQR**, serta dilakukan **log transform dan clipping** untuk menstabilkan distribusi data.
---
## 📊 Exploratory Data Analysis

### Target Distribution
Distribusi target menunjukkan dataset **tidak seimbang**:
- Kelas 0 (lancar bayar): **92%**
- Kelas 1 (gagal bayar): **8%**

### Demographic Insights
- Nasabah **perempuan** memiliki risiko gagal bayar lebih rendah dibanding laki-laki.
- Nasabah yang **memiliki mobil** cenderung memiliki risiko kredit lebih rendah.
- **Pensioner dan state servant** memiliki risiko gagal bayar paling rendah dibanding segmen pekerjaan lainnya.

### Financial Risk Insights
- Nasabah dengan **Very High Income** memiliki tingkat kelancaran pembayaran tertinggi.
- Risiko gagal bayar tertinggi muncul pada kategori **Medium Credit**.
- Beban cicilan yang terlalu tinggi dapat meningkatkan potensi risiko kredit.
### Behavior Insights
- Nasabah dengan **masa kerja lebih dari 10 tahun** memiliki tingkat pembayaran paling stabil.
- Nasabah yang **baru mengganti nomor telepon** memiliki kecenderungan risiko lebih tinggi dibanding nasabah yang lama menggunakan nomor yang sama.
---
## ⚙️ Feature Engineering

Beberapa tahapan feature engineering yang dilakukan:

**Feature Selection**
- Menghapus fitur dengan korelasi > 90% untuk mengurangi multikolinearitas.

**Encoding**
- **Binary Encoding**  
  `NAME_CONTRACT_TYPE`, `CODE_GENDER`, `FLAG_OWN_CAR`, `FLAG_OWN_REALTY`

- **One Hot Encoding**  
  Digunakan pada fitur seperti:
  `NAME_INCOME_TYPE`, `NAME_EDUCATION_TYPE`, `NAME_FAMILY_STATUS`, dll.

**Balancing Data**
- Mengatasi ketidakseimbangan kelas menggunakan metode **SMOTE (Synthetic Minority Oversampling Technique)**.

---
##  🤖 Modeling
Model yang diuji dalam penelitian ini:

- Logistic Regression
- Logistic Regression + Scaling
- Decision Tree
- Random Forest
- Extra Trees
- XGBoost

Model dievaluasi menggunakan metrik:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC AUC
---

## 🏆 Best Model Result
Model terbaik yang diperoleh adalah **XGBoost** dengan performa:

- ROC AUC tertinggi
- F1-score kelas minoritas paling baik
- Keseimbangan precision dan recall yang optimal

---

## 📊 Model Evaluation

Hasil evaluasi model pada data uji:

- **True Positive:** 1.546 nasabah berhasil terdeteksi sebagai berisiko gagal bayar
- **True Negative:** 51.630 nasabah terdeteksi dengan benar sebagai nasabah lancar
- **False Positive:** 4.908 nasabah lancar terdeteksi sebagai berisiko
- **False Negative:** 3.419 nasabah gagal bayar tidak terdeteksi oleh model

---
## 🔍 Feature Importance (XGBoost)

Beberapa fitur yang paling berpengaruh terhadap risiko kredit:

- Tingkat pendidikan
- Kepemilikan mobil
- Kepemilikan telepon
- Pendapatan nasabah
- Riwayat kredit
- Jumlah anggota keluarga
- Stabilitas pekerjaan

Faktor-faktor ini mencerminkan **stabilitas finansial dan perilaku pembayaran nasabah**.

---
## 💡 Business Recommendations
Berdasarkan hasil analisis dan pemodelan, beberapa rekomendasi yang dapat diterapkan:
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

## 👩‍💻 Author
Project by: Khamidah Arsyad Daud

Machine Learning & Data Analysis Enthusiast
