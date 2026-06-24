# Prediksi Diabetes Menggunakan Algoritma Machine Learning

## Nama Anggota Kelompok
- Enggar Tri Rahmadhani (103132400007)
- Rimbhi Putri Aulia Azzahra (103132400018)
- Rebeca Grace Catlia Wahyudi (103132400015)

---

## Deskripsi Permasalahan

Diabetes Mellitus adalah salah satu penyakit kronis yang menjadi masalah kesehatan global. Deteksi dini sangat penting untuk mencegah komplikasi serius seperti gagal ginjal, kebutaan, dan penyakit jantung. Namun, diagnosis diabetes seringkali memerlukan pemeriksaan laboratorium yang tidak selalu terjangkau oleh semua kalangan.

**Permasalahan:** Bagaimana memprediksi risiko diabetes seseorang berdasarkan data kesehatan seperti usia, BMI, kadar gula darah, dan riwayat kesehatan lainnya menggunakan pendekatan Machine Learning?

**Tujuan:** Membangun model Machine Learning yang akurat untuk memprediksi apakah seseorang menderita diabetes atau tidak berdasarkan fitur-fitur kesehatan yang tersedia.

---

## Sumber dan Deskripsi Dataset

**Sumber Dataset:**  
[Diabetes Prediction Dataset - Kaggle](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset)

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

Target:
- 0 = Tidak diabetes
- 1 = Diabetes
---

## Tahapan Preprocessing
### 1. Pemeriksaan Missing Value

Melakukan pengecekan data yang hilang (missing value) pada setiap fitur untuk memastikan kualitas data sebelum diproses lebih lanjut.

### 2. Pemeriksaan dan Penghapusan Data Duplikat

Melakukan identifikasi data duplikat kemudian menghapusnya agar tidak memengaruhi hasil pelatihan model.

### 3. Encoding Data Kategorikal

Mengubah data kategorikal menjadi data numerik menggunakan Label Encoder pada fitur:

- gender
- smoking_history

### 4. Pemisahan Fitur dan Target

Dataset dipisahkan menjadi:

- Fitur (X)
- Target (y)

Target yang digunakan adalah variabel **diabetes**.

### 5. Pembagian Data Latih dan Data Uji

Dataset dibagi menjadi:

- Data Latih (80%)
- Data Uji (20%)

menggunakan metode `train_test_split()`.

### 6. Penyeimbangan Data Menggunakan SMOTE

Karena distribusi kelas diabetes tidak seimbang, digunakan metode SMOTE (Synthetic Minority Oversampling Technique) untuk menambah jumlah data pada kelas minoritas.

### 7. Standarisasi Data

Melakukan standarisasi menggunakan StandardScaler agar seluruh fitur memiliki skala yang ser


---

## Metode yang Digunakan

Model Machine Learning yang digunakan dan dibandingkan:

| No | Model | Deskripsi |
|----|-------|-----------|
| 1 | Logistic Regression | Model linear sederhana sebagai baseline |
| 2 | Decision Tree | Model berbasis pohon keputusan |
| 3 | Random Forest | Ensemble Decision Tree dengan bagging |
| 4 | K-Nearest Neighbors (KNN) | Berbasis jarak antar data |
| 5 | XGBoost | Algoritma boosting yang powerful |

---
## Cara Menjalankan Program

### Menggunakan Google Collab

1. Buka Google Collab.
2. Upload file `ipynb`.
3. Upload dataset `diabetes_prediction_dataset.csv`.
4. Jalankan seluruh cell dari atas hingga bawah.

### Output Program

Program akan menghasilkan:

- Distribusi Data Diabetes/target
- Distribusi BMI
- Distribusi Glukosa
- Correlation Heatmap 
- Perbandingan Performa Model
- Feature Importance
- Confusion Matrix Model Terbaik
- Nilai Accuracy, Precision, Recall, F1-Score, dan ROC-AUC dari setiap model
  
---
## Hasil Eksperimen dan Evaluasi

Pada penelitian ini dilakukan perbandingan performa lima algoritma Machine Learning, yaitu:

- Logistic Regression
- Decision Tree
- Random Forest
- K-Nearest Neighbor (KNN)
- XGBoost

Evaluasi model dilakukan menggunakan metrik Accuracy, Precision, Recall, F1-Score, dan ROC-AUC.

Hasil pengujian menunjukkan bahwa model XGBoost memberikan performa terbaik dibandingkan model lainnya. Hal ini ditunjukkan oleh nilai evaluasi yang lebih tinggi pada sebagian besar metrik yang digunakan.

Selain evaluasi menggunakan metrik klasifikasi, dilakukan pula analisis menggunakan Confusion Matrix untuk melihat kemampuan model dalam mengklasifikasikan data diabetes dan non-diabetes secara lebih rinci.

### Perbandingan Model

Model-model yang diuji kemudian dibandingkan berdasarkan nilai F1-Score karena metrik ini mempertimbangkan keseimbangan antara Precision dan Recall, terutama pada data yang memiliki distribusi kelas tidak seimbang.

Berdasarkan hasil perbandingan, urutan performa model dari yang terbaik hingga terendah adalah:

1. XGBoost
2. Random Forest
3. K-Nearest Neighbor (KNN)
4. Decision Tree
5. Logistic Regression

### Analisis Model Terbaik

XGBoost dipilih sebagai model terbaik karena mampu menghasilkan performa klasifikasi yang lebih baik dibandingkan algoritma lainnya. Algoritma ini menggunakan metode boosting yang memperbaiki kesalahan prediksi secara bertahap sehingga mampu menangkap pola kompleks pada data kesehatan pasien.

### Evaluasi Feature Importance

Analisis Feature Importance menunjukkan bahwa fitur yang paling berpengaruh terhadap prediksi diabetes adalah:

- HbA1c Level
- Blood Glucose Level
- Age
- BMI

Hasil tersebut sesuai dengan faktor medis yang umum digunakan dalam diagnosis diabetes sehingga mendukung validitas model yang dibangun.

---
## Kesimpulan

Pada proyek ini berhasil dibangun model Machine Learning untuk memprediksi risiko diabetes berdasarkan data kesehatan pasien. Proses pengolahan data meliputi pemeriksaan missing value, penghapusan data duplikat, encoding data kategorikal, pembagian data latih dan data uji, penyeimbangan data menggunakan SMOTE, serta standarisasi data.

Lima algoritma Machine Learning dibandingkan, yaitu Logistic Regression, Decision Tree, Random Forest, K-Nearest Neighbor (KNN), dan XGBoost. Berdasarkan hasil evaluasi menggunakan Accuracy, Precision, Recall, F1-Score, dan ROC-AUC, model XGBoost menunjukkan performa terbaik dalam mengklasifikasikan pasien diabetes dan non-diabetes.

Selain itu, hasil analisis feature importance menunjukkan bahwa HbA1c Level, Blood Glucose Level, Age, dan BMI merupakan fitur yang paling berpengaruh terhadap prediksi diabetes. Dengan demikian, model yang dibangun dapat digunakan sebagai alat bantu untuk mendukung deteksi dini risiko diabetes berdasarkan data kesehatan pasien.
