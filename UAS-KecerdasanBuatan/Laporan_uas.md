# Laporan Proyek Machine Learning - Sistem Prediksi Cuaca Harian Kabupaten Garut
# Nenden Nurdianti (2406113) - Informatika B

## Domain Proyek

Cuaca merupakan salah satu faktor yang sangat mempengaruhi berbagai sektor kehidupan, seperti pertanian, transportasi, perikanan, dan mitigasi bencana. Prediksi kondisi cuaca yang akurat dapat membantu masyarakat maupun instansi terkait dalam mengambil keputusan yang tepat. 

Dengan perkembangan *Artificial Intelligence* (AI), proses prediksi cuaca dapat dilakukan menggunakan teknik *Machine Learning* yang mampu mengenali pola dari data historis. Model klasifikasi dapat digunakan untuk memprediksi kategori kondisi cuaca berdasarkan beberapa parameter meteorologi.

### Referensi
# Referensi

1. Alzahrani, A., Alghamdi, A., Alghamdi, A., & Alshamrani, A. (2022). Deterministic Weather Forecasting Models Based on Intelligent Predictors: A Survey. *Journal of King Saud University – Computer and Information Sciences*. https://doi.org/10.1016/j.jksuci.2020.11.006

2. Bauer, P., Dueben, P. D., Hoefler, T., et al. (2022). ESA-ECMWF Report on Recent Progress and Research Directions in Machine Learning for Earth System Observation and Prediction. *npj Climate and Atmospheric Science, 5*(59). https://doi.org/10.1038/s41612-022-00269-z

3. Sharma, P., Kumar, R., & Singh, A. (2024). Comparative Analysis of Weather Prediction Using Classification Algorithm: Random Forest Classifier, Decision Tree Classifier and Extra Tree Classifier. *International Journal of Research Publication and Reviews*.

4. Sari, R., Pratama, A., & Nugroho, D. (2023). Implementasi Algoritma K-Nearest Neighbor untuk Klasifikasi Cuaca. *Jurnal Algoritme*.

5. Pedregosa, F., Varoquaux, G., Gramfort, A., Michel, V., Thirion, B., Grisel, O., Blondel, M., Prettenhofer, P., Weiss, R., Dubourg, V., Vanderplas, J., Passos, A., Cournapeau, D., Brucher, M., Perrot, M., & Duchesnay, É. (2011). Scikit-learn: Machine Learning in Python. *Journal of Machine Learning Research, 12*, 2825–2830.

## Business Understanding

### Problem Statements
1. Bagaimana membangun model *Machine Learning* yang mampu mengklasifikasikan kondisi cuaca di Kabupaten Garut secara otomatis berdasarkan data meteorologi historis?
2. Algoritma mana antara *K-Nearest Neighbor* (KNN) dan *Decision Tree Classifier* yang memberikan performa dan akurasi terbaik untuk memprediksi cuaca harian?

### Goals
* Menganalisis karakteristik dataset cuaca Kabupaten Garut melalui analisis data eksploratif (EDA).
* Membangun model klasifikasi menggunakan algoritma *Decision Tree* dan *K-Nearest Neighbor* (KNN).
* Membandingkan performa kedua algoritma dan menentukan model terbaik berdasarkan metrik evaluasi klasifikasi (*Accuracy*, *Precision*, *Recall*, dan *F1-Score*).

### Solution Statement
Untuk mencapai tujuan proyek, langkah-langkah solusi berikut diimplementasikan:
1. **Eksplorasi dan Pemahaman Data (EDA):** Melakukan analisis deskriptif, pemeriksaan *missing value*, pendeteksian data duplikat, dan visualisasi fitur meteorologi untuk memahami karakteristik dataset.
2. **Data Preparation:** Melakukan *scaling* data numerik menggunakan `StandardScaler` dan *encoding* target menggunakan `LabelEncoder` agar siap diproses oleh algoritma.
3. **Implementasi Dua Algoritma Klasifikasi:** Membangun *pipeline* pemodelan menggunakan *K-Nearest Neighbor* (KNN) dan *Decision Tree Classifier*.
4. **Evaluasi Performa Komparatif:** Mengevaluasi dan membandingkan performa kedua model menggunakan matriks evaluasi lengkap seperti *Classification Report* dan *Confusion Matrix*.

---

## Data Understanding

### Deskripsi Dataset
Dataset yang digunakan adalah **dataset_cuaca_garut_5000.csv** yang berisi 5.000 data observasi cuaca harian di Kabupaten Garut dengan 7 kolom (6 fitur numerik dan 1 target kategorikal).

### Informasi Dataset
Berdasarkan fungsi `df.info()`, dataset tidak memiliki nilai kosong (*missing value*) ataupun baris duplikat. Berikut adalah struktur kolom dataset:

| Kolom | Tipe Data | Jumlah Data | Deskripsi |
| :--- | :--- | :--- | :--- |
| **Suhu_C** | float64 | 5,000 | Suhu udara dalam satuan Celsius |
| **Kelembaban_persen** | int64 | 5,000 | Tingkat kelembapan udara dalam persen |
| **Tekanan_Udara_hPa** | float64 | 5,000 | Tekanan udara dalam satuan hPa |
| **Kecepatan_Angin_kmjam**| float64 | 5,000 | Kecepatan angin dalam km/jam |
| **Arah_Angin_derajat** | int64 | 5,000 | Arah hembusan angin dalam derajat (0°-359°) |
| **Curah_Hujan_mm** | float64 | 5,000 | Volume curah hujan dalam satuan milimeter |
| **Kondisi_Cuaca** | object | 5,000 | Target prediksi klasifikasi (**Cerah**, **Berawan**, **Hujan**) |

### Statistik Deskriptif
Berikut adalah ringkasan statistik dari `df.describe()` untuk fitur-fitur numerik:

| Fitur | Count | Mean | Std Dev | Min | 25% | 50% | 75% | Max |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Suhu_C** | 5,000 | 24.09 | 4.62 | 16.00 | 20.10 | 24.10 | 28.10 | 32.00 |
| **Kelembaban_persen** | 5,000 | 76.39 | 12.39 | 55.00 | 66.00 | 76.50 | 87.00 | 98.00 |
| **Tekanan_Udara_hPa** | 5,000 | 1008.53 | 2.59 | 1004.00| 1006.30| 1008.55| 1010.80| 1013.00|
| **Kecepatan_Angin_kmjam**| 5,000 | 16.53 | 7.79 | 3.00 | 9.80 | 16.80 | 23.30 | 30.00 |
| **Arah_Angin_derajat** | 5,000 | 175.85 | 103.62 | 0.00 | 85.00 | 176.00 | 264.00 | 359.00 |
| **Curah_Hujan_mm** | 5,000 | 3.76 | 8.00 | 0.00 | 0.00 | 1.80 | 3.60 | 49.80 |

### Exploratory Data Analysis (EDA)
1. **Pemeriksaan Kualitas Data:** Hasil pemanggilan `df.isnull().sum()` menunjukkan angka 0 untuk seluruh kolom, mengindikasikan data bersih dari *missing value*. Duplikasi data juga bernilai 0.
2. **Karakteristik Distribusi:** Fitur atmosferik seperti Suhu, Kelembapan, dan Tekanan memiliki sebaran yang cukup merata dan normal di seluruh rentang nilai minimum hingga maksimumnya.
3. **Fitur Kunci:** Variabel `Curah_Hujan_mm` memiliki korelasi intuitif yang sangat kuat langsung terhadap penentuan label target `Kondisi_Cuaca` (misalnya nilai curah hujan tinggi hampir selalu diklasifikasikan sebagai Hujan).

---

## Data Preparation

Proses penyiapan data dilakukan secara terstruktur agar model klasifikasi dapat melatih data dengan efisien dan tanpa bias skala:

1. **Pemisahan Fitur dan Target:**
   * Fitur ($X$): Kolom `Suhu_C`, `Kelembaban_persen`, `Tekanan_Udara_hPa`, `Kecepatan_Angin_kmjam`, `Arah_Angin_derajat`, dan `Curah_Hujan_mm`.
   * Target ($y$): Kolom `Kondisi_Cuaca` yang berisi kelas kategorikal.

2. **Encoding Label Target:**
   Menggunakan `LabelEncoder` untuk mengubah kelas string (`Cerah`, `Berawan`, `Hujan`) menjadi representasi numerik (`0`, `1`, `2`) yang dapat dipahami oleh fungsi loss algoritma.

3. **Pembagian Data Latih dan Uji (Train-Test Split):**
   Dataset dibagi menjadi **80% untuk data latih** (*training set*) dan **20% untuk data uji** (*testing set*). Pembagian ini dilakukan secara acak terkontrol menggunakan parameter `random_state` guna menjaga konsistensi pengujian.

4. **Standarisasi Fitur (Feature Scaling):**
   Menggunakan `StandardScaler` untuk menyamakan skala seluruh fitur numerik agar memiliki nilai rata-rata (*mean*) = 0 dan varians = 1. Langkah standarisasi ini sangat kritikal terutama bagi algoritma berbasis jarak seperti **KNN** agar fitur berangka besar (seperti `Arah_Angin_derajat`) tidak mendominasi perhitungan jarak dibanding fitur berangka kecil.

---

## Modeling

Dua buah algoritma pembelajaran diawasi (*supervised learning*) diterapkan pada proyek ini menggunakan objek *Pipeline* dari Scikit-Learn:

### 1. K-Nearest Neighbor (KNN)
* **Cara Kerja:** KNN melakukan klasifikasi berdasarkan analogi kedekatan jarak antar data. Data uji baru akan diklasifikasikan berdasarkan suara mayoritas dari label $K$ tetangga terdekatnya.
* **Parameter:** Menggunakan jumlah tetangga standar $K=5$ dengan fungsi perhitungan jarak Euclidean standar.
* **Kelebihan:** Sederhana, tangguh terhadap data ber-noise, dan sangat efektif jika jumlah data latihnya besar.
* **Kekurangan:** Sensitif terhadap fitur yang tidak relevan/tidak discaling, serta beban komputasi pengujian cenderung tinggi karena harus menghitung jarak ke seluruh poin data.

### 2. Decision Tree Classifier
* **Cara Kerja:** Algoritma ini membangun model klasifikasi berbentuk struktur pohon keputusan. Algoritma melakukan partisi data secara rekursif berdasarkan fitur yang menghasilkan penurunan nilai entropi (*Information Gain*) atau *Gini Impurity* tertinggi.
* **Parameter:** Parameter standar dengan `random_state` konstan untuk menjamin replikasi pohon keputusan yang sama.
* **Kelebihan:** Mudah diinterpretasikan, tidak memerlukan asumsi distribusi data, dan mampu menangani hubungan non-linear antar fitur secara alami.
* **Kekurangan:** Rentan mengalami *overfitting* jika pohon dibiarkan tumbuh terlalu dalam tanpa dilakukan pemangkasan (*pruning*).

---

## Evaluation

Evaluasi performa model dilakukan menggunakan data uji (20% dari total dataset). Metrik utama yang digunakan adalah **Accuracy**, **Precision**, **Recall**, dan **F1-Score**.

### Perbandingan Hasil Evaluasi Model
Berdasarkan hasil pengujian kedua arsitektur model klasifikasi di atas, diperoleh performa sebagai berikut:

| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: | :---: |
| **K-Nearest Neighbor (KNN)** | High | High | High | High |
| **Decision Tree Classifier** | 1.00 (Perfect) | 1.00 | 1.00 | 1.00 |

### Analisis Hasil Evaluasi
* **Performa Decision Tree:** Model Decision Tree berhasil mengklasifikasikan seluruh data uji secara sempurna (Akurasi 100%). Hal ini dimungkinkan karena adanya fitur penentu yang sangat eksplisit, yaitu variabel `Curah_Hujan_mm` dan pola batas kondisi cuaca harian dalam dataset ini terpisah secara linear dan jelas (misalnya: jika `Curah_Hujan_mm` $> 0$, otomatis terlabel Hujan atau Berawan). 
* **Performa KNN:** Algoritma KNN juga memberikan tingkat akurasi yang sangat tinggi berkat proses standarisasi data (`StandardScaler`) yang matang pada tahap *data preparation*.

### Kesimpulan Akhir
Kedua model bekerja sangat baik untuk melakukan prediksi cuaca harian Kabupaten Garut. Namun, **Decision Tree Classifier** dipilih sebagai model terbaik untuk sistem ini karena menghasilkan performa klasifikasi yang mutlak tanpa *error*, serta menawarkan keunggulan komputasi pengujian yang jauh lebih cepat dibandingkan KNN yang harus menghitung matriks jarak setiap kali ada data baru masuk.