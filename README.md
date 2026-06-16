# Statistika-dan-Probabilitas-B_Nur-Aisyah_F55123042

# Prediksi Biaya Asuransi Kesehatan 
## Deskripsi Proyek

Proyek ini bertujuan untuk membangun model Machine Learning yang dapat memprediksi biaya asuransi kesehatan seseorang berdasarkan karakteristik individu. Prediksi dilakukan menggunakan tiga algoritma regresi, yaitu:

* K-Nearest Neighbor (KNN)
* Random Forest Regressor
* AdaBoost Regressor

Dataset yang digunakan adalah **Medical Cost Personal Dataset** yang berisi informasi mengenai usia, jenis kelamin, BMI, jumlah anak, status merokok, wilayah tempat tinggal, serta biaya asuransi kesehatan yang dibayarkan oleh individu.

---

## Studi Kasus

Perusahaan asuransi kesehatan perlu menentukan biaya premi yang sesuai dengan profil calon nasabah. Penentuan premi yang tidak akurat dapat menyebabkan kerugian bagi perusahaan maupun ketidakadilan bagi pelanggan.

Melalui pendekatan Machine Learning, data historis nasabah digunakan untuk menemukan pola hubungan antara karakteristik individu dan biaya asuransi kesehatan yang harus dibayarkan. Model yang dihasilkan diharapkan mampu membantu proses estimasi biaya secara lebih objektif dan berbasis data.

---

## Dataset

Dataset terdiri dari 1.338 data dengan atribut sebagai berikut:

| Fitur    | Keterangan                        |
| -------- | --------------------------------- |
| age      | Usia individu                     |
| sex      | Jenis kelamin                     |
| bmi      | Body Mass Index                   |
| children | Jumlah anak tanggungan            |
| smoker   | Status merokok                    |
| region   | Wilayah tempat tinggal            |
| charges  | Biaya asuransi kesehatan (target) |

---

## Tahapan Proyek

### 1. Persiapan Data

* Memuat dataset menggunakan Pandas.
* Memeriksa struktur dan tipe data.
* Mengidentifikasi fitur numerik dan kategorikal.

### 2. Penanganan Outlier

* Visualisasi menggunakan Boxplot.
* Deteksi outlier pada variabel BMI dan Charges.
* Penghapusan outlier menggunakan metode Interquartile Range (IQR).

### 3. Exploratory Data Analysis (EDA)

Dilakukan analisis univariat dan multivariat untuk memahami karakteristik data.

Temuan penting:

* Mayoritas individu merupakan non-perokok.
* Perokok memiliki biaya asuransi jauh lebih tinggi dibanding non-perokok.
* Wilayah Southeast memiliki rata-rata biaya asuransi tertinggi.
* Variabel BMI dan jumlah anak memiliki korelasi yang sangat rendah terhadap biaya asuransi.

### 4. Data Preparation

* One-Hot Encoding untuk fitur kategorikal.
* Pembagian data menjadi data latih dan data uji.
* Standardisasi fitur numerik menggunakan StandardScaler.

### 5. Pemodelan

Tiga algoritma regresi digunakan:

1. K-Nearest Neighbor (KNN)
2. Random Forest Regressor
3. AdaBoost Regressor

### 6. Evaluasi Model

Evaluasi dilakukan menggunakan metrik Mean Squared Error (MSE) dan perbandingan hasil prediksi pada data uji.

---

## Hasil dan Analisis

Berdasarkan hasil eksperimen:

### Faktor yang Berpengaruh

Faktor yang paling memengaruhi biaya asuransi kesehatan adalah:

* Status merokok (smoker)
* Usia (age)
* Wilayah tempat tinggal (region)

Sementara itu, BMI dan jumlah anak memiliki pengaruh yang relatif kecil terhadap biaya asuransi.

### Perbandingan Model

| Model         | Performa Training | Performa Testing |
| ------------- | ----------------- | ---------------- |
| KNN           | Sedang            | Sedang           |
| Random Forest | Terbaik           | Sedang           |
| AdaBoost      | Sedang            | Terbaik          |

Hasil menunjukkan bahwa:

* Random Forest menghasilkan performa terbaik pada data training.
* AdaBoost menghasilkan performa terbaik pada data testing.
* AdaBoost memiliki kemampuan generalisasi yang lebih baik untuk memprediksi data baru.

### Uji Prediksi

Pada salah satu sampel data uji:

* Nilai aktual: 5934.38
* Prediksi KNN: 5937.69

KNN menghasilkan selisih prediksi hanya sekitar 3.31 sehingga menjadi model yang paling mendekati nilai aktual pada pengujian sampel tersebut.

---

## Kesimpulan

Proyek ini berhasil membangun model prediksi biaya asuransi kesehatan menggunakan algoritma KNN, Random Forest, dan AdaBoost. Berdasarkan evaluasi keseluruhan, AdaBoost menunjukkan performa terbaik dalam melakukan prediksi pada data baru, sedangkan Random Forest unggul pada data pelatihan. Faktor yang paling memengaruhi biaya asuransi adalah status merokok, usia, dan wilayah tempat tinggal.

---

## Teknologi yang Digunakan

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn

---

## Pengembangan Selanjutnya

Beberapa peningkatan yang dapat dilakukan:

* Hyperparameter Tuning menggunakan GridSearchCV.
* Cross Validation untuk evaluasi yang lebih stabil.
* Penambahan fitur kesehatan yang lebih lengkap.
* Implementasi algoritma lain seperti XGBoost, Gradient Boosting, atau Neural Network.
