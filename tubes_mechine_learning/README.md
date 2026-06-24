# 🩺 Prediksi Diabetes Menggunakan Algoritma Machine Learning

## 📋 Nama Anggota Kelompok
- **Nama Anggota 1** (NIM)
- **Nama Anggota 2** (NIM)
- **Nama Anggota 3** (NIM) *[opsional, maksimal 3]*

---

## 📖 Deskripsi Permasalahan

Diabetes Mellitus adalah salah satu penyakit kronis yang menjadi masalah kesehatan global. Deteksi dini sangat penting untuk mencegah komplikasi serius seperti gagal ginjal, kebutaan, dan penyakit jantung. Namun, diagnosis diabetes seringkali memerlukan pemeriksaan laboratorium yang tidak selalu terjangkau oleh semua kalangan.

**Permasalahan:** Bagaimana memprediksi risiko diabetes seseorang berdasarkan data kesehatan seperti usia, BMI, kadar gula darah, dan riwayat kesehatan lainnya menggunakan pendekatan Machine Learning?

**Tujuan:** Membangun model Machine Learning yang akurat untuk memprediksi apakah seseorang menderita diabetes atau tidak berdasarkan fitur-fitur kesehatan yang tersedia.

---

## 📂 Sumber dan Deskripsi Dataset

**Sumber Dataset:**  
[Diabetes Prediction Dataset - Kaggle](https://www.kaggle.com/datasets/akshaydattatraykhare/diabetes-dataset)

**Deskripsi Dataset:**  
Dataset ini berisi 100.000 data pasien dengan 9 fitur, antara lain:

| Fitur | Deskripsi |
|-------|-----------|
| `gender` | Jenis kelamin (Female, Male, Other) |
| `age` | Usia (tahun) |
| `hypertension` | Riwayat hipertensi (0 = Tidak, 1 = Ya) |
| `heart_disease` | Riwayat penyakit jantung (0 = Tidak, 1 = Ya) |
| `smoking_history` | Riwayat merokok (never, former, current, etc.) |
| `bmi` | Indeks Massa Tubuh (BMI) |
| `HbA1c_level` | Kadar HbA1c (%) |
| `blood_glucose_level` | Kadar gula darah (mg/dL) |
| `diabetes` | **Target:** Status diabetes (0 = Tidak, 1 = Ya) |

---

## 🔧 Tahapan Preprocessing

1. **Penghapusan Data Duplikat**  
   Terdapat 3.854 data duplikat yang dihapus agar tidak terjadi bias.

2. **Encoding Data Kategorikal**  
   Fitur `gender` dan `smoking_history` diubah menjadi numerik menggunakan **LabelEncoder**.

3. **Pemisahan Fitur dan Target**  
   `X` = semua fitur kecuali `diabetes`  
   `y` = kolom `diabetes`

4. **Train-Test Split**  
   Data dibagi menjadi 80% training dan 20% testing dengan stratifikasi.

5. **Penanganan Data Tidak Seimbang (Imbalanced Data)**  
   Menggunakan **SMOTE (Synthetic Minority Over-sampling Technique)** untuk menyeimbangkan kelas diabetes (kelas minoritas) pada data training.

6. **Standardisasi**  
   Fitur numerik dinormalisasi menggunakan **StandardScaler**.

---

## 🤖 Metode yang Digunakan

Model Machine Learning yang digunakan dan dibandingkan:

| No | Model | Deskripsi |
|----|-------|-----------|
| 1 | Logistic Regression | Model linear sederhana sebagai baseline |
| 2 | Decision Tree | Model berbasis pohon keputusan |
| 3 | Random Forest | Ensemble Decision Tree dengan bagging |
| 4 | K-Nearest Neighbors (KNN) | Berbasis jarak antar data |
| 5 | XGBoost | Algoritma boosting yang powerful |

**Metrik Evaluasi:**  
- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC

---

## 🚀 Cara Menjalankan Program

### 1. Clone Repository
```bash
git clone https://github.com/username/repository-name.git
cd repository-name