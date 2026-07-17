# Laporan Proyek Machine Learning
# Sistem Prediksi Cuaca Harian Kabupaten Garut Menggunakan Algoritma K-Nearest Neighbor (KNN) dan Decision Tree

**Nama :** Nenden Nurdianti

**NIM :** 2406113

**Program Studi :** Teknik Informatika

**Mata Kuliah :** Kecerdasan Buatan

**Institut Teknologi Garut**

---

# Domain Proyek

## Latar Belakang

Cuaca merupakan kondisi atmosfer pada suatu wilayah dalam periode waktu tertentu yang dipengaruhi oleh berbagai faktor meteorologi seperti suhu udara, kelembapan udara, tekanan atmosfer, kecepatan angin, arah angin, dan curah hujan. Informasi mengenai kondisi cuaca memiliki peranan yang sangat penting dalam mendukung berbagai aktivitas manusia. Banyak sektor kehidupan yang sangat bergantung pada kondisi cuaca, di antaranya sektor pertanian, transportasi, penerbangan, perikanan, pariwisata, konstruksi, hingga mitigasi bencana alam.

Kabupaten Garut merupakan salah satu wilayah di Provinsi Jawa Barat yang memiliki karakteristik geografis yang cukup beragam, mulai dari dataran rendah, pegunungan, hingga kawasan pesisir selatan. Kondisi geografis tersebut menyebabkan perubahan cuaca di Kabupaten Garut relatif dinamis sehingga sering terjadi perubahan kondisi atmosfer dalam waktu yang singkat. Ketidakpastian kondisi cuaca dapat memberikan dampak terhadap aktivitas masyarakat sehari-hari maupun kegiatan ekonomi di daerah tersebut.

Dalam sektor pertanian misalnya, informasi mengenai kemungkinan terjadinya hujan sangat diperlukan oleh petani untuk menentukan waktu tanam maupun panen. Pada sektor transportasi, informasi cuaca membantu pengemudi dalam mempersiapkan perjalanan sehingga dapat mengurangi risiko kecelakaan akibat hujan deras atau kabut. Selain itu, instansi pemerintah juga memerlukan informasi cuaca sebagai dasar dalam pengambilan keputusan terkait mitigasi bencana seperti banjir, tanah longsor, maupun angin kencang.

Selama ini prediksi cuaca umumnya dilakukan menggunakan pendekatan numerik yang membutuhkan proses komputasi yang kompleks serta data pengamatan atmosfer dalam jumlah besar. Walaupun metode tersebut memiliki tingkat akurasi yang tinggi, implementasinya memerlukan sumber daya komputasi yang besar serta pemodelan fisika atmosfer yang cukup rumit. Oleh karena itu, diperlukan pendekatan alternatif yang lebih sederhana namun tetap mampu menghasilkan prediksi yang baik.

Perkembangan teknologi Artificial Intelligence (AI), khususnya Machine Learning, memberikan peluang baru dalam pengembangan sistem prediksi cuaca. Machine Learning memungkinkan komputer mempelajari pola hubungan antarvariabel dari data historis tanpa harus diprogram menggunakan aturan yang eksplisit. Dengan memanfaatkan data historis cuaca, algoritma Machine Learning mampu menemukan pola yang sulit diamati secara manual sehingga dapat digunakan untuk melakukan prediksi kondisi cuaca pada data baru.

Machine Learning sendiri telah banyak diterapkan dalam berbagai bidang, seperti kesehatan, pendidikan, keuangan, pertanian, keamanan siber, hingga prediksi iklim. Pada bidang meteorologi, Machine Learning mulai banyak digunakan sebagai metode pelengkap sistem prediksi cuaca konvensional karena mampu melakukan proses klasifikasi maupun prediksi dengan waktu komputasi yang relatif cepat.

Pada penelitian ini digunakan pendekatan klasifikasi untuk mengelompokkan kondisi cuaca menjadi tiga kategori utama, yaitu **Cerah**, **Berawan**, dan **Hujan**. Proses klasifikasi dilakukan berdasarkan enam parameter meteorologi yang terdiri atas suhu udara, kelembapan udara, tekanan udara, kecepatan angin, arah angin, serta curah hujan. Keenam parameter tersebut dipilih karena merupakan variabel yang umum digunakan dalam analisis kondisi atmosfer dan memiliki pengaruh terhadap perubahan cuaca.

Penelitian ini membandingkan dua algoritma klasifikasi yang cukup populer, yaitu **K-Nearest Neighbor (KNN)** dan **Decision Tree**. Algoritma K-Nearest Neighbor merupakan metode klasifikasi berbasis kedekatan jarak antar data sehingga proses pengambilan keputusan dilakukan berdasarkan mayoritas kelas dari sejumlah tetangga terdekat. Algoritma ini dikenal sederhana, mudah diimplementasikan, serta memiliki performa yang baik pada berbagai kasus klasifikasi apabila data telah melalui proses normalisasi.

Sementara itu, Decision Tree merupakan algoritma klasifikasi yang membangun struktur pohon keputusan berdasarkan atribut yang paling informatif dalam memisahkan kelas data. Decision Tree memiliki keunggulan dalam menghasilkan model yang mudah dipahami karena setiap keputusan direpresentasikan dalam bentuk aturan (rule). Selain itu, algoritma ini mampu menangani hubungan non-linear antarvariabel dan tidak memerlukan proses standarisasi data seperti pada algoritma berbasis jarak.

Perbandingan kedua algoritma tersebut dilakukan untuk mengetahui metode mana yang memiliki performa terbaik dalam mengklasifikasikan kondisi cuaca pada dataset yang digunakan. Hasil penelitian diharapkan dapat memberikan gambaran mengenai efektivitas penggunaan algoritma Machine Learning dalam bidang prediksi cuaca sekaligus menjadi referensi bagi penelitian selanjutnya yang menggunakan dataset cuaca aktual dari Badan Meteorologi, Klimatologi, dan Geofisika (BMKG).

Selain memberikan kontribusi dalam pengembangan model prediksi cuaca, penelitian ini juga diharapkan dapat menjadi media pembelajaran mengenai implementasi Machine Learning mulai dari proses eksplorasi data, persiapan data, pembangunan model, hingga evaluasi performa menggunakan berbagai metrik klasifikasi. Dengan demikian, penelitian ini tidak hanya menghasilkan model klasifikasi yang mampu memprediksi kondisi cuaca, tetapi juga memberikan pemahaman mengenai tahapan pengembangan sistem Machine Learning secara lengkap.

---

## Referensi

Alzahrani, A., Alghamdi, A., Alghamdi, A., & Alshamrani, A. (2022). *Deterministic Weather Forecasting Models Based on Intelligent Predictors: A Survey*. Journal of King Saud University – Computer and Information Sciences.

Bauer, P., Dueben, P. D., Hoefler, T., et al. (2022). *ESA-ECMWF Report on Recent Progress and Research Directions in Machine Learning for Earth System Observation and Prediction*. npj Climate and Atmospheric Science.

Sharma, P., Kumar, R., & Singh, A. (2024). *Comparative Analysis of Weather Prediction Using Classification Algorithm*. International Journal of Research Publication and Reviews.

# Business Understanding

Business Understanding merupakan tahapan awal dalam metodologi pengembangan proyek Machine Learning yang bertujuan untuk memahami permasalahan yang akan diselesaikan, menentukan tujuan penelitian, merumuskan solusi yang akan diterapkan, serta menetapkan indikator keberhasilan model. Tahapan ini sangat penting karena menjadi dasar dalam menentukan proses pengolahan data, pemilihan algoritma, hingga evaluasi model yang akan dibangun.

Pada penelitian ini, fokus utama adalah membangun model klasifikasi kondisi cuaca harian di Kabupaten Garut berdasarkan parameter-parameter meteorologi menggunakan algoritma Machine Learning. Model yang dihasilkan diharapkan mampu membantu proses pengambilan keputusan melalui prediksi kondisi cuaca yang cepat dan akurat.

---

## Problem Statements

Berdasarkan latar belakang penelitian, beberapa permasalahan yang akan diselesaikan pada proyek ini adalah sebagai berikut.

1. Bagaimana membangun model Machine Learning yang mampu mengklasifikasikan kondisi cuaca harian di Kabupaten Garut berdasarkan parameter meteorologi seperti suhu udara, kelembapan udara, tekanan udara, kecepatan angin, arah angin, dan curah hujan?

2. Bagaimana melakukan proses pengolahan data (data preprocessing) agar dataset siap digunakan dalam proses pelatihan model Machine Learning?

3. Algoritma klasifikasi manakah yang memberikan performa terbaik dalam melakukan klasifikasi kondisi cuaca, yaitu **K-Nearest Neighbor (KNN)** atau **Decision Tree Classifier**?

4. Bagaimana mengevaluasi kualitas model klasifikasi menggunakan metrik evaluasi seperti Accuracy, Precision, Recall, F1-Score, dan Confusion Matrix sehingga diperoleh model yang paling optimal?

5. Faktor atau variabel meteorologi apa yang paling berpengaruh terhadap proses klasifikasi kondisi cuaca berdasarkan hasil pembelajaran model Machine Learning?

---

## Goals

Berdasarkan rumusan masalah di atas, tujuan yang ingin dicapai dalam penelitian ini adalah sebagai berikut.

1. Mengembangkan model klasifikasi kondisi cuaca harian menggunakan pendekatan Machine Learning berdasarkan data meteorologi.

2. Melakukan eksplorasi dan analisis karakteristik dataset melalui proses Exploratory Data Analysis (EDA) sehingga diperoleh pemahaman mengenai pola distribusi data.

3. Melakukan proses Data Preparation yang meliputi pemeriksaan kualitas data, encoding label, pembagian data latih dan data uji, serta standarisasi data agar siap digunakan dalam proses pelatihan model.

4. Membangun model klasifikasi menggunakan algoritma **K-Nearest Neighbor (KNN)**.

5. Membangun model klasifikasi menggunakan algoritma **Decision Tree Classifier**.

6. Membandingkan performa kedua algoritma menggunakan berbagai metrik evaluasi klasifikasi sehingga dapat diketahui algoritma yang memberikan hasil terbaik.

7. Menghasilkan model Machine Learning yang mampu mengklasifikasikan kondisi cuaca secara akurat sehingga dapat dijadikan dasar dalam pengembangan sistem prediksi cuaca berbasis Artificial Intelligence.

---

## Solution Statement

Untuk mencapai tujuan penelitian tersebut, beberapa solusi yang diimplementasikan dalam proyek ini adalah sebagai berikut.

### 1. Data Understanding dan Exploratory Data Analysis (EDA)

Tahap pertama dilakukan untuk memahami karakteristik dataset yang digunakan. Proses ini meliputi pemeriksaan struktur data, tipe data, jumlah observasi, nilai statistik deskriptif, distribusi data, identifikasi missing value, pemeriksaan data duplikat, serta analisis hubungan antarvariabel menggunakan berbagai visualisasi seperti histogram, boxplot, countplot, dan heatmap korelasi.

Tahapan ini bertujuan memastikan bahwa dataset memiliki kualitas yang baik sebelum digunakan dalam proses pemodelan.

---

### 2. Data Preparation

Tahapan berikutnya adalah melakukan persiapan data agar dapat diproses oleh algoritma Machine Learning.

Langkah-langkah yang dilakukan meliputi:

- Memisahkan variabel independen (fitur) dan variabel dependen (target).
- Mengubah label kategori menjadi data numerik menggunakan **LabelEncoder**.
- Membagi dataset menjadi data latih (80%) dan data uji (20%).
- Melakukan standarisasi fitur menggunakan **StandardScaler**, khususnya untuk meningkatkan performa algoritma KNN yang sensitif terhadap perbedaan skala data.

Tahapan preprocessing ini bertujuan menghasilkan dataset yang lebih konsisten sehingga model dapat mempelajari pola data secara optimal.

---

### 3. Implementasi Algoritma K-Nearest Neighbor (KNN)

Model pertama yang digunakan adalah algoritma K-Nearest Neighbor (KNN). Algoritma ini melakukan klasifikasi berdasarkan kedekatan jarak antar data menggunakan metode Euclidean Distance.

Pada penelitian ini digunakan nilai parameter **K = 5**, sehingga setiap data baru akan diklasifikasikan berdasarkan mayoritas kelas dari lima tetangga terdekat.

Implementasi algoritma ini bertujuan mengetahui kemampuan metode berbasis jarak dalam mengenali pola kondisi cuaca.

---

### 4. Implementasi Algoritma Decision Tree

Model kedua menggunakan algoritma Decision Tree Classifier.

Decision Tree membangun struktur pohon keputusan berdasarkan fitur yang memiliki kemampuan terbaik dalam memisahkan setiap kelas data menggunakan kriteria Information Gain maupun Gini Impurity.

Keunggulan algoritma ini adalah mampu menghasilkan model yang mudah dipahami karena seluruh proses pengambilan keputusan direpresentasikan dalam bentuk aturan (rule) yang bersifat interpretable.

---

### 5. Evaluasi dan Perbandingan Model

Setelah kedua model selesai dilatih, dilakukan evaluasi performa menggunakan data pengujian.

Evaluasi dilakukan menggunakan beberapa metrik klasifikasi, yaitu:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Classification Report

Hasil evaluasi kemudian dibandingkan sehingga dapat diketahui algoritma yang memberikan performa terbaik pada dataset cuaca Kabupaten Garut.

---

## Success Metrics

Keberhasilan penelitian ini diukur berdasarkan kualitas model klasifikasi yang dihasilkan. Model dikatakan berhasil apabila memenuhi beberapa indikator berikut.

| Metrik | Target |
|---------|--------|
| Accuracy | ≥ 90% |
| Precision | ≥ 90% |
| Recall | ≥ 90% |
| F1-Score | ≥ 90% |
| Confusion Matrix | Memiliki jumlah prediksi benar yang dominan pada setiap kelas |

Selain metrik evaluasi tersebut, keberhasilan penelitian juga ditentukan oleh kemampuan model dalam melakukan klasifikasi terhadap data baru secara konsisten tanpa mengalami penurunan performa yang signifikan.

---

## Manfaat Penelitian

Penelitian ini diharapkan dapat memberikan manfaat baik secara akademis maupun praktis.

### 1. Manfaat Akademis

- Menjadi referensi bagi penelitian selanjutnya mengenai penerapan Machine Learning pada bidang meteorologi.
- Memberikan contoh implementasi algoritma klasifikasi menggunakan Python dan Scikit-Learn.
- Menambah literatur mengenai perbandingan algoritma KNN dan Decision Tree pada permasalahan klasifikasi cuaca.

### 2. Manfaat Praktis

- Membantu proses prediksi kondisi cuaca secara otomatis.
- Memberikan gambaran awal mengenai potensi penggunaan Artificial Intelligence dalam bidang meteorologi.
- Menjadi dasar pengembangan sistem prediksi cuaca berbasis web maupun aplikasi mobile.
- Mendukung pengambilan keputusan pada sektor pertanian, transportasi, pariwisata, dan mitigasi bencana.

---

## Alur Penyelesaian Masalah

Secara umum tahapan penyelesaian masalah pada penelitian ini dapat digambarkan sebagai berikut.

1. Mengumpulkan dataset cuaca.
2. Memahami karakteristik data melalui Data Understanding.
3. Melakukan Exploratory Data Analysis (EDA).
4. Melakukan Data Preparation.
5. Membangun model K-Nearest Neighbor.
6. Membangun model Decision Tree.
7. Melakukan pengujian model menggunakan data testing.
8. Mengevaluasi performa model menggunakan berbagai metrik klasifikasi.
9. Membandingkan hasil kedua algoritma.
10. Menentukan model terbaik berdasarkan hasil evaluasi.

Tahapan tersebut mengikuti alur kerja proyek Machine Learning yang sistematis sehingga seluruh proses mulai dari pengolahan data hingga evaluasi model dapat dilakukan secara terstruktur dan menghasilkan model klasifikasi yang memiliki performa optimal.

# Data Understanding

Tahap **Data Understanding** merupakan proses awal dalam pengembangan model Machine Learning yang bertujuan untuk memahami karakteristik dataset sebelum dilakukan proses pemodelan. Pada tahap ini dilakukan identifikasi struktur data, jenis data, kualitas data, statistik deskriptif, distribusi data, serta hubungan antarvariabel yang terdapat dalam dataset.

Pemahaman terhadap dataset sangat penting karena kualitas data yang baik akan sangat memengaruhi performa model Machine Learning. Selain itu, proses ini juga bertujuan untuk mengetahui apakah dataset memerlukan proses pembersihan data (*data cleaning*) ataupun transformasi sebelum memasuki tahap *Data Preparation*.

Dataset yang digunakan dalam penelitian ini merupakan dataset sintetis yang dibuat untuk kebutuhan pembelajaran Machine Learning dengan jumlah **5.000 observasi**. Dataset tersebut merepresentasikan kondisi cuaca harian Kabupaten Garut berdasarkan beberapa parameter meteorologi yang umum digunakan dalam analisis cuaca.

---

# Deskripsi Dataset

Dataset yang digunakan bernama:

```
dataset_cuaca_garut_5000.csv
```

Dataset terdiri dari **7 atribut**, yaitu enam atribut sebagai variabel independen (*features*) dan satu atribut sebagai variabel dependen (*target*).

Target yang akan diprediksi adalah kondisi cuaca yang terdiri atas tiga kelas yaitu:

- Cerah
- Berawan
- Hujan

Setiap baris data merepresentasikan satu observasi kondisi cuaca harian berdasarkan kombinasi beberapa parameter atmosfer.

---

# Informasi Dataset

Berdasarkan hasil pemeriksaan menggunakan fungsi:

```python
df.info()
```

diperoleh informasi bahwa dataset memiliki sebanyak **5.000 baris data** dengan **7 kolom**. Seluruh data numerik telah tersimpan menggunakan tipe data **float64** maupun **int64**, sedangkan variabel target menggunakan tipe data **object** karena masih berbentuk kategori.

Selain itu, hasil pemeriksaan menunjukkan bahwa seluruh atribut memiliki jumlah data yang sama sehingga tidak ditemukan adanya nilai yang hilang (*missing value*).

Tabel berikut menunjukkan struktur dataset.

| Kolom | Tipe Data | Jumlah Data | Keterangan |
|---------|------------|------------|----------------------------|
| Suhu_C | float64 | 5000 | Suhu udara (°C) |
| Kelembaban_persen | int64 | 5000 | Persentase kelembapan udara |
| Tekanan_Udara_hPa | float64 | 5000 | Tekanan atmosfer |
| Kecepatan_Angin_kmjam | float64 | 5000 | Kecepatan angin |
| Arah_Angin_derajat | int64 | 5000 | Arah angin |
| Curah_Hujan_mm | float64 | 5000 | Curah hujan |
| Kondisi_Cuaca | Object | 5000 | Label target |

Berdasarkan informasi tersebut dapat disimpulkan bahwa seluruh atribut telah memiliki tipe data yang sesuai sehingga tidak diperlukan proses konversi tipe data sebelum dilakukan pemodelan.

---

# Deskripsi Setiap Variabel

## 1. Suhu_C

Variabel **Suhu_C** menunjukkan temperatur udara dalam satuan derajat Celcius.

Suhu merupakan salah satu parameter meteorologi yang sangat berpengaruh terhadap kondisi atmosfer. Perubahan suhu memengaruhi proses penguapan air, pembentukan awan, hingga terjadinya hujan.

Secara umum suhu yang tinggi meningkatkan proses evaporasi sehingga kandungan uap air di atmosfer menjadi lebih besar.

---

## 2. Kelembaban_persen

Variabel ini menunjukkan kandungan uap air yang terdapat di udara.

Semakin tinggi kelembapan udara maka kemungkinan terbentuknya awan dan hujan akan semakin besar. Oleh karena itu variabel ini diperkirakan memiliki hubungan yang cukup kuat terhadap kondisi cuaca.

---

## 3. Tekanan_Udara_hPa

Tekanan udara merupakan gaya yang diberikan oleh massa udara terhadap permukaan bumi.

Perubahan tekanan udara sering digunakan sebagai indikator perubahan cuaca. Tekanan udara yang rendah biasanya berasosiasi dengan pembentukan awan dan hujan, sedangkan tekanan udara tinggi cenderung menunjukkan kondisi cuaca cerah.

---

## 4. Kecepatan_Angin_kmjam

Variabel ini menunjukkan kecepatan perpindahan massa udara.

Kecepatan angin memengaruhi distribusi awan serta penyebaran uap air di atmosfer sehingga dapat memengaruhi perubahan kondisi cuaca.

---

## 5. Arah_Angin_derajat

Variabel arah angin menunjukkan arah datangnya angin dengan rentang nilai 0° hingga 359°.

Informasi arah angin dapat membantu menjelaskan asal massa udara yang masuk ke suatu wilayah sehingga berpengaruh terhadap kondisi atmosfer setempat.

---

## 6. Curah_Hujan_mm

Curah hujan merupakan jumlah air hujan yang turun dalam satuan milimeter.

Variabel ini diperkirakan menjadi salah satu variabel yang paling berpengaruh terhadap klasifikasi kondisi cuaca karena secara langsung menggambarkan intensitas hujan yang terjadi.

---

## 7. Kondisi_Cuaca

Variabel ini merupakan target klasifikasi yang terdiri atas tiga kategori yaitu:

- Cerah
- Berawan
- Hujan

Model Machine Learning akan mempelajari hubungan antara keenam variabel meteorologi dengan label target tersebut.

---

# Pemeriksaan Kualitas Data

Kualitas data merupakan faktor penting dalam membangun model Machine Learning.

Oleh karena itu dilakukan beberapa pemeriksaan sebagai berikut.

## Missing Value

Pemeriksaan dilakukan menggunakan:

```python
df.isnull().sum()
```

Hasil pemeriksaan menunjukkan bahwa seluruh kolom memiliki nilai **0**, sehingga dapat disimpulkan bahwa dataset tidak memiliki *missing value*.

Kondisi ini menunjukkan bahwa proses imputasi data tidak diperlukan.

---

## Data Duplikat

Selanjutnya dilakukan pemeriksaan data duplikat menggunakan:

```python
df.duplicated().sum()
```

Hasil pemeriksaan menunjukkan tidak terdapat data yang terduplikasi.

Dengan demikian setiap observasi pada dataset merupakan data yang unik.

---

## Konsistensi Data

Pemeriksaan juga dilakukan terhadap tipe data dan rentang nilai setiap atribut.

Seluruh atribut numerik berada pada rentang nilai yang masih logis berdasarkan karakteristik meteorologi.

Sebagai contoh:

- Suhu berada pada rentang 16–32°C
- Kelembapan berada pada rentang 55–98%
- Tekanan udara berada pada rentang 1004–1013 hPa
- Curah hujan berada pada rentang 0–49 mm

Rentang tersebut masih sesuai dengan kondisi cuaca tropis di Indonesia.

---

# Statistik Deskriptif

Statistik deskriptif digunakan untuk memberikan gambaran umum mengenai distribusi data.

Berdasarkan hasil fungsi:

```python
df.describe()
```

diperoleh informasi sebagai berikut.

| Variabel | Mean | Standar Deviasi | Minimum | Maksimum |
|-----------|-------|----------------|----------|-----------|
| Suhu | 24.09 | 4.62 | 16 | 32 |
| Kelembapan | 76.39 | 12.39 | 55 | 98 |
| Tekanan Udara | 1008.53 | 2.59 | 1004 | 1013 |
| Kecepatan Angin | 16.53 | 7.79 | 3 | 30 |
| Arah Angin | 175.85 | 103.62 | 0 | 359 |
| Curah Hujan | 3.76 | 8.00 | 0 | 49.8 |

Nilai rata-rata dan standar deviasi menunjukkan bahwa variasi data masih berada pada rentang yang wajar dan tidak terdapat penyimpangan yang ekstrem.

---

# Distribusi Target

Distribusi jumlah data pada masing-masing kelas perlu diperhatikan untuk memastikan tidak terjadi **class imbalance**.

Apabila jumlah setiap kelas relatif seimbang, maka model Machine Learning akan memiliki peluang yang lebih baik dalam mempelajari karakteristik setiap kelas.

Distribusi target divisualisasikan menggunakan **Countplot** sehingga dapat diketahui proporsi data Cerah, Berawan, dan Hujan.

Dataset yang memiliki distribusi kelas yang seimbang akan menghasilkan model klasifikasi yang lebih stabil dibandingkan dataset yang didominasi oleh satu kelas tertentu.

---

# Kesimpulan Data Understanding

Berdasarkan hasil proses Data Understanding dapat disimpulkan bahwa dataset memiliki kualitas yang sangat baik untuk digunakan pada penelitian ini.

Tidak ditemukan nilai yang hilang, data duplikat, maupun kesalahan tipe data. Seluruh variabel memiliki rentang nilai yang masih logis sesuai karakteristik data meteorologi.

Selain itu, keenam variabel meteorologi diperkirakan memiliki kontribusi terhadap proses klasifikasi kondisi cuaca, khususnya variabel **Curah_Hujan_mm**, **Kelembaban_persen**, dan **Tekanan_Udara_hPa** yang secara teoritis memiliki hubungan erat dengan pembentukan kondisi atmosfer.

Hasil analisis pada tahap ini menjadi dasar untuk melanjutkan proses **Exploratory Data Analysis (EDA)** dan **Data Preparation** sebelum dilakukan pembangunan model Machine Learning menggunakan algoritma K-Nearest Neighbor dan Decision Tree.

# Exploratory Data Analysis (EDA)

## Pendahuluan

Exploratory Data Analysis (EDA) merupakan tahapan penting dalam proses pengembangan model Machine Learning. Tahap ini bertujuan untuk memahami karakteristik data melalui berbagai teknik visualisasi maupun analisis statistik sehingga dapat diketahui pola, distribusi, hubungan antarvariabel, serta potensi permasalahan pada dataset.

Melalui proses EDA, peneliti dapat memperoleh gambaran awal mengenai karakteristik setiap fitur yang nantinya akan digunakan dalam proses pelatihan model Machine Learning. Informasi tersebut sangat penting untuk menentukan teknik preprocessing yang sesuai serta membantu memilih algoritma yang tepat.

Pada penelitian ini, proses EDA dilakukan menggunakan beberapa jenis visualisasi, yaitu:

- Histogram
- Boxplot
- Countplot
- Heatmap Korelasi
- Pairplot (Opsional)
- Scatter Plot

Visualisasi tersebut digunakan untuk mengetahui distribusi data, mendeteksi outlier, melihat keseimbangan kelas target, serta menganalisis hubungan antarvariabel meteorologi.

---

# Pemeriksaan Missing Value

Sebelum melakukan visualisasi data, langkah pertama adalah memastikan bahwa dataset tidak memiliki nilai yang hilang (*missing value*).

Pemeriksaan dilakukan menggunakan fungsi berikut.

```python
df.isnull().sum()
```

Hasil pemeriksaan menunjukkan bahwa seluruh atribut memiliki nilai **0** sehingga tidak ditemukan missing value pada dataset.

Kondisi ini menunjukkan bahwa kualitas dataset sudah sangat baik dan tidak memerlukan proses imputasi data sebelum dilakukan analisis lebih lanjut.

Selain itu dilakukan pula pemeriksaan data duplikat menggunakan fungsi:

```python
df.duplicated().sum()
```

Hasil pemeriksaan menunjukkan bahwa tidak terdapat data yang terduplikasi sehingga seluruh observasi merupakan data yang unik.

---

# Distribusi Variabel Menggunakan Histogram

Histogram digunakan untuk melihat bagaimana distribusi nilai pada masing-masing variabel numerik.

Visualisasi dilakukan menggunakan kode berikut.

```python
df.hist(figsize=(15,10))
plt.show()
```

Histogram memberikan gambaran mengenai:

- Persebaran data
- Nilai yang paling sering muncul
- Bentuk distribusi
- Kemungkinan adanya skewness
- Kemungkinan adanya outlier

### Analisis Histogram

### Suhu Udara

Distribusi suhu terlihat relatif simetris dengan rentang nilai antara **16°C hingga 32°C**.

Sebagian besar data berada di sekitar nilai rata-rata yaitu sekitar **24°C**, sehingga dapat dikatakan bahwa distribusi suhu mendekati distribusi normal.

Kondisi tersebut menunjukkan bahwa suhu udara pada dataset memiliki variasi yang masih wajar dan tidak didominasi oleh nilai ekstrem.

---

### Kelembapan Udara

Histogram kelembapan menunjukkan sebagian besar data berada pada rentang **65–90%**.

Distribusi kelembapan cukup merata dan menunjukkan bahwa wilayah penelitian memiliki tingkat kelembapan yang relatif tinggi, sesuai karakteristik wilayah tropis.

Nilai kelembapan yang tinggi umumnya berkaitan dengan meningkatnya peluang terbentuknya awan maupun hujan.

---

### Tekanan Udara

Tekanan udara memiliki distribusi yang cukup sempit.

Sebagian besar data berada di sekitar **1008 hPa**, menunjukkan bahwa tekanan udara relatif stabil.

Distribusi yang stabil mengindikasikan bahwa tekanan udara tidak mengalami fluktuasi ekstrem.

---

### Kecepatan Angin

Kecepatan angin memiliki distribusi yang cukup merata.

Nilai kecepatan angin berkisar antara **3 km/jam hingga 30 km/jam**.

Sebagian besar observasi berada pada kategori kecepatan sedang sehingga diharapkan tidak memberikan pengaruh ekstrem terhadap proses klasifikasi.

---

### Arah Angin

Distribusi arah angin relatif menyebar pada rentang **0° hingga 359°**.

Hal ini menunjukkan bahwa arah datangnya angin cukup bervariasi sehingga dapat memberikan informasi tambahan mengenai kondisi atmosfer.

---

### Curah Hujan

Histogram curah hujan menunjukkan distribusi yang cenderung **right-skewed**.

Sebagian besar data memiliki curah hujan rendah, sedangkan sebagian kecil memiliki curah hujan tinggi.

Distribusi tersebut masih wajar karena pada kondisi nyata, hari tanpa hujan maupun hujan ringan biasanya lebih banyak dibandingkan hujan dengan intensitas tinggi.

---

# Analisis Outlier Menggunakan Boxplot

Boxplot digunakan untuk mendeteksi adanya nilai pencilan (*outlier*) pada setiap variabel numerik.

Visualisasi dilakukan menggunakan kode berikut.

```python
sns.boxplot(data=df)
```

Boxplot memperlihatkan:

- Nilai minimum
- Kuartil pertama
- Median
- Kuartil ketiga
- Nilai maksimum
- Outlier

### Analisis Boxplot

Berdasarkan hasil visualisasi, sebagian besar fitur tidak menunjukkan adanya outlier ekstrem.

Beberapa nilai pada variabel Curah Hujan berada di luar rentang interkuartil.

Namun kondisi tersebut masih dapat diterima karena hujan dengan intensitas tinggi memang merupakan fenomena yang dapat terjadi pada kondisi cuaca tertentu.

Oleh karena itu proses penghapusan outlier tidak dilakukan agar informasi penting tetap dipertahankan.

---

# Distribusi Kelas Target Menggunakan Countplot

Countplot digunakan untuk mengetahui jumlah data pada masing-masing kelas target.

Visualisasi dilakukan menggunakan kode berikut.

```python
sns.countplot(data=df,x='Kondisi_Cuaca')
```

### Analisis Countplot

Distribusi kelas target menunjukkan jumlah data pada masing-masing kategori cuaca.

Keseimbangan jumlah data antar kelas sangat penting karena akan memengaruhi kemampuan model dalam mempelajari karakteristik masing-masing kategori.

Apabila salah satu kelas memiliki jumlah data yang jauh lebih banyak dibandingkan kelas lainnya, maka model berpotensi mengalami **class imbalance**.

Pada dataset penelitian ini distribusi kelas relatif seimbang sehingga risiko bias model menjadi lebih kecil.

Kondisi tersebut mendukung proses pelatihan model agar mampu mengenali seluruh kategori cuaca dengan baik.

---

# Analisis Korelasi Menggunakan Heatmap

Heatmap digunakan untuk mengetahui hubungan antarvariabel numerik.

Visualisasi dilakukan menggunakan kode berikut.

```python
sns.heatmap(df.corr(numeric_only=True),
            annot=True,
            cmap='coolwarm')
```

Heatmap menghasilkan matriks korelasi menggunakan koefisien Pearson.

Nilai korelasi berada pada rentang:

- -1 = hubungan negatif sempurna
- 0 = tidak terdapat hubungan
- +1 = hubungan positif sempurna

### Analisis Heatmap

Berdasarkan heatmap dapat diketahui bahwa beberapa variabel memiliki hubungan yang cukup kuat terhadap kondisi cuaca.

Variabel Curah Hujan menunjukkan hubungan paling dominan terhadap perubahan kondisi cuaca.

Selain itu kelembapan udara juga memiliki kecenderungan berkorelasi positif terhadap curah hujan.

Sebaliknya suhu udara cenderung memiliki hubungan negatif terhadap kelembapan.

Hubungan tersebut sesuai dengan teori meteorologi yang menyatakan bahwa peningkatan kelembapan akan meningkatkan peluang pembentukan awan dan hujan.

Heatmap juga menunjukkan bahwa tidak terdapat multikolinearitas yang sangat tinggi antar fitur sehingga seluruh variabel masih layak digunakan sebagai input model.

---

# Pairplot

Pairplot digunakan untuk melihat hubungan antar pasangan variabel numerik.

Visualisasi dilakukan menggunakan:

```python
sns.pairplot(df,
             hue='Kondisi_Cuaca')
```

Melalui pairplot dapat diamati pola pemisahan antar kelas.

Apabila terdapat kelompok data yang terpisah secara jelas, maka kemungkinan besar algoritma klasifikasi mampu membangun model dengan performa yang tinggi.

Pada dataset penelitian ini terlihat bahwa beberapa pasangan fitur menunjukkan pemisahan kelas yang cukup jelas, terutama ketika melibatkan variabel Curah Hujan dan Kelembapan.

Hal tersebut menjadi indikasi awal bahwa dataset memiliki karakteristik yang cukup baik untuk proses klasifikasi.

---

# Scatter Plot

Scatter plot digunakan untuk melihat hubungan antara dua variabel numerik tertentu.

Sebagai contoh hubungan antara:

- Suhu dan Kelembapan
- Curah Hujan dan Kelembapan
- Curah Hujan dan Tekanan Udara

Visualisasi ini membantu memahami pola penyebaran data secara lebih rinci.

Hasil scatter plot menunjukkan bahwa data tidak membentuk hubungan linear sempurna, sehingga penggunaan algoritma Decision Tree yang mampu menangani hubungan non-linear menjadi salah satu pilihan yang tepat.

---

# Insight Hasil EDA

Berdasarkan seluruh proses Exploratory Data Analysis, diperoleh beberapa temuan penting sebagai berikut.

1. Dataset memiliki kualitas yang sangat baik karena tidak ditemukan missing value maupun data duplikat.

2. Distribusi seluruh fitur berada pada rentang nilai yang masih logis sesuai karakteristik meteorologi.

3. Curah Hujan merupakan variabel yang memiliki pengaruh paling besar terhadap proses klasifikasi kondisi cuaca.

4. Kelembapan udara menunjukkan hubungan yang cukup kuat terhadap pembentukan hujan.

5. Tekanan udara relatif stabil sehingga memberikan kontribusi sebagai variabel pendukung.

6. Distribusi kelas target relatif seimbang sehingga risiko bias model cukup kecil.

7. Tidak ditemukan multikolinearitas yang sangat tinggi antar fitur sehingga seluruh variabel dapat digunakan sebagai input model.

8. Pairplot menunjukkan adanya pola pemisahan kelas yang cukup jelas sehingga diharapkan model Machine Learning mampu menghasilkan akurasi yang tinggi.

---

# Kesimpulan Exploratory Data Analysis

Tahap Exploratory Data Analysis memberikan pemahaman yang lebih mendalam mengenai karakteristik dataset sebelum dilakukan proses pemodelan.

Hasil analisis menunjukkan bahwa dataset telah memenuhi kualitas yang baik untuk digunakan dalam pembangunan model Machine Learning. Tidak ditemukan permasalahan serius seperti missing value, data duplikat, maupun outlier ekstrem yang dapat mengganggu proses pelatihan model.

Selain itu, analisis korelasi menunjukkan bahwa variabel Curah Hujan, Kelembapan Udara, dan Suhu merupakan variabel yang paling berkontribusi terhadap proses klasifikasi kondisi cuaca. Temuan ini menjadi dasar dalam proses Data Preparation dan Modeling menggunakan algoritma K-Nearest Neighbor (KNN) serta Decision Tree pada tahap berikutnya.

# Data Preparation

## Pendahuluan

Data Preparation merupakan tahapan yang bertujuan untuk mempersiapkan dataset sebelum digunakan pada proses pembangunan model Machine Learning. Tahapan ini sangat penting karena kualitas data yang telah diproses akan sangat memengaruhi kemampuan model dalam mempelajari pola yang terdapat pada dataset.

Pada tahap sebelumnya telah dilakukan proses **Data Understanding** dan **Exploratory Data Analysis (EDA)** untuk memahami karakteristik dataset. Berdasarkan hasil analisis tersebut diketahui bahwa dataset memiliki kualitas yang baik karena tidak ditemukan nilai yang hilang (*missing value*), data duplikat, maupun kesalahan tipe data. Oleh karena itu, proses Data Preparation pada penelitian ini lebih difokuskan pada transformasi data agar sesuai dengan kebutuhan algoritma klasifikasi yang digunakan.

Tahapan Data Preparation pada penelitian ini terdiri atas beberapa proses, yaitu:

1. Pemilihan fitur (Feature Selection)
2. Pemisahan fitur dan target
3. Label Encoding
4. Pembagian data latih dan data uji (*Train-Test Split*)
5. Standarisasi data menggunakan *StandardScaler*

Setiap tahapan dilakukan secara berurutan agar data yang digunakan pada proses pelatihan model memiliki kualitas yang optimal.

---

# Feature Selection

Tahap pertama dalam Data Preparation adalah menentukan atribut yang akan digunakan sebagai variabel masukan (*input features*) dan variabel keluaran (*target*).

Pada penelitian ini dipilih enam atribut meteorologi sebagai variabel independen karena secara teoritis memiliki hubungan terhadap perubahan kondisi cuaca.

Variabel tersebut meliputi:

| Variabel | Fungsi |
|-----------|------------------------------|
| Suhu_C | Mengukur temperatur udara |
| Kelembaban_persen | Mengukur kadar uap air di udara |
| Tekanan_Udara_hPa | Mengukur tekanan atmosfer |
| Kecepatan_Angin_kmjam | Mengukur kecepatan angin |
| Arah_Angin_derajat | Mengukur arah datang angin |
| Curah_Hujan_mm | Mengukur intensitas hujan |

Sedangkan variabel target yang akan diprediksi adalah:

```
Kondisi_Cuaca
```

yang terdiri atas tiga kelas yaitu:

- Cerah
- Berawan
- Hujan

Proses pemilihan fitur dilakukan menggunakan kode berikut.

```python
X = df.drop("Kondisi_Cuaca", axis=1)
y = df["Kondisi_Cuaca"]
```

Melalui proses tersebut diperoleh:

- **X** sebagai variabel independen (*features*)
- **y** sebagai variabel dependen (*target*)

Pemisahan ini diperlukan karena algoritma Machine Learning hanya dapat mempelajari hubungan antara variabel masukan dan variabel target apabila keduanya dipisahkan terlebih dahulu.

---

# Label Encoding

Variabel target masih berbentuk data kategorikal berupa teks, yaitu:

- Cerah
- Berawan
- Hujan

Sebagian besar algoritma Machine Learning pada pustaka Scikit-Learn hanya dapat memproses data numerik. Oleh karena itu dilakukan proses **Label Encoding** untuk mengubah data kategorikal menjadi representasi numerik.

Transformasi dilakukan menggunakan kelas **LabelEncoder** dari Scikit-Learn.

```python
from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

y = le.fit_transform(y)
```

Setelah proses encoding selesai, setiap kategori memiliki representasi numerik sebagai berikut.

| Kondisi Cuaca | Label |
|---------------|-------|
| Cerah | 0 |
| Berawan | 1 |
| Hujan | 2 |

Perubahan ini tidak mengubah makna data, melainkan hanya mengubah format penyimpanan agar dapat diproses oleh algoritma klasifikasi.

---

# Train-Test Split

Setelah proses encoding selesai, dataset dibagi menjadi dua bagian, yaitu:

- Data Latih (*Training Set*)
- Data Uji (*Testing Set*)

Pembagian dataset bertujuan untuk mengevaluasi kemampuan model dalam melakukan prediksi terhadap data yang belum pernah dipelajari sebelumnya.

Pada penelitian ini digunakan rasio:

- 80% data latih
- 20% data uji

Pembagian dilakukan menggunakan fungsi:

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

Parameter `random_state = 42` digunakan agar proses pembagian data selalu menghasilkan hasil yang sama setiap kali program dijalankan.

Dengan demikian proses eksperimen menjadi lebih konsisten dan dapat direproduksi oleh peneliti lain.

Apabila dataset terdiri atas 5.000 data maka hasil pembagian menjadi:

| Dataset | Jumlah Data |
|----------|-------------|
| Training | 4.000 |
| Testing | 1.000 |

Sebagian besar data digunakan sebagai data pelatihan agar model dapat mempelajari pola secara optimal, sedangkan sebagian lainnya digunakan untuk menguji kemampuan generalisasi model.

---

# Feature Scaling Menggunakan StandardScaler

Tahapan berikutnya adalah melakukan standarisasi data.

Standarisasi dilakukan menggunakan **StandardScaler**.

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

X_train = scaler.fit_transform(X_train)

X_test = scaler.transform(X_test)
```

Standardisasi bertujuan mengubah seluruh fitur sehingga memiliki:

- Mean = 0
- Standard Deviation = 1

Proses ini sangat penting terutama pada algoritma **K-Nearest Neighbor (KNN)**.

Hal tersebut disebabkan karena KNN menggunakan perhitungan jarak Euclidean sehingga fitur yang memiliki rentang nilai lebih besar akan lebih mendominasi proses perhitungan jarak.

Sebagai contoh:

```
Arah Angin
0 - 359

Suhu
16 - 32
```

Tanpa dilakukan standarisasi, variabel arah angin akan memberikan pengaruh jauh lebih besar dibandingkan suhu meskipun secara teoritis belum tentu lebih penting.

Dengan menggunakan StandardScaler seluruh fitur memiliki skala yang sama sehingga proses klasifikasi menjadi lebih adil.

Perlu diketahui bahwa proses standarisasi hanya dilakukan menggunakan data training.

Selanjutnya parameter hasil standarisasi tersebut diterapkan pada data testing.

Hal ini bertujuan untuk menghindari **data leakage**, yaitu kondisi ketika informasi dari data uji ikut digunakan pada proses pelatihan model.

---

# Alur Data Preparation

Secara keseluruhan proses Data Preparation dapat digambarkan sebagai berikut.

```
Dataset

      │

      ▼

Feature Selection

      │

      ▼

Label Encoding

      │

      ▼

Train Test Split

      │

      ▼

StandardScaler

      │

      ▼

Training Data

Testing Data
```

Diagram tersebut menunjukkan bahwa seluruh proses preprocessing dilakukan sebelum model Machine Learning dibangun.

---

# Ringkasan Tahapan Data Preparation

| Tahapan | Tujuan |
|----------|------------------------------------------------|
| Feature Selection | Menentukan fitur dan target |
| Label Encoding | Mengubah kategori menjadi numerik |
| Train-Test Split | Membagi data latih dan data uji |
| StandardScaler | Menyamakan skala seluruh fitur |
| Output | Dataset siap digunakan oleh model |

---

# Alasan Pemilihan Teknik Preprocessing

Beberapa teknik preprocessing dipilih berdasarkan karakteristik dataset dan kebutuhan algoritma.

**Feature Selection** dilakukan agar model hanya menggunakan atribut yang relevan terhadap proses klasifikasi.

**Label Encoding** dipilih karena variabel target masih berupa kategori teks sehingga perlu diubah menjadi data numerik.

**Train-Test Split** digunakan agar performa model dapat dievaluasi menggunakan data yang belum pernah dipelajari sebelumnya.

**StandardScaler** digunakan karena algoritma KNN sangat sensitif terhadap skala data. Sebaliknya, Decision Tree sebenarnya tidak memerlukan standarisasi, namun proses ini tetap dilakukan agar kedua algoritma menggunakan dataset yang sama sehingga perbandingan performa menjadi lebih adil.

---

# Kesimpulan Data Preparation

Tahap Data Preparation berhasil menghasilkan dataset yang siap digunakan dalam proses pembangunan model Machine Learning.

Seluruh fitur telah dipisahkan dari variabel target, label kategori berhasil diubah menjadi bentuk numerik, dataset telah dibagi menjadi data pelatihan dan data pengujian, serta seluruh fitur numerik telah distandarisasi menggunakan StandardScaler.

Dengan selesainya tahap ini, dataset telah memenuhi seluruh kebutuhan algoritma K-Nearest Neighbor maupun Decision Tree sehingga proses pembangunan model dapat dilakukan secara optimal pada tahap berikutnya.

# Modeling

## Pendahuluan

Tahap **Modeling** merupakan inti dari proses Machine Learning, yaitu membangun model yang mampu mempelajari pola hubungan antara variabel input dengan variabel target berdasarkan data pelatihan (*training data*). Pada penelitian ini digunakan pendekatan **Supervised Learning**, karena dataset yang digunakan telah memiliki label target berupa kondisi cuaca.

Tujuan utama dari tahap ini adalah menghasilkan model klasifikasi yang mampu mengidentifikasi kondisi cuaca berdasarkan enam parameter meteorologi, yaitu suhu udara, kelembapan udara, tekanan udara, kecepatan angin, arah angin, dan curah hujan.

Pada penelitian ini dilakukan implementasi dan perbandingan dua algoritma klasifikasi, yaitu:

1. **K-Nearest Neighbor (KNN)**
2. **Decision Tree Classifier**

Pemilihan kedua algoritma tersebut didasarkan pada karakteristiknya yang berbeda. KNN merupakan algoritma berbasis jarak (*distance-based algorithm*), sedangkan Decision Tree merupakan algoritma berbasis aturan (*rule-based algorithm*). Dengan membandingkan kedua algoritma tersebut, diharapkan dapat diketahui metode yang paling sesuai untuk melakukan klasifikasi kondisi cuaca.

---

# Model 1 : K-Nearest Neighbor (KNN)

## Pengertian KNN

K-Nearest Neighbor (KNN) merupakan salah satu algoritma klasifikasi yang paling sederhana dalam Machine Learning. Algoritma ini bekerja dengan mencari sejumlah data latih yang memiliki jarak paling dekat terhadap data baru, kemudian menentukan kelas berdasarkan mayoritas tetangga terdekat tersebut.

Berbeda dengan algoritma lain, KNN tidak membangun model matematis pada saat proses pelatihan. Seluruh data latih akan disimpan, kemudian proses klasifikasi dilakukan ketika terdapat data baru yang akan diprediksi. Oleh karena itu, KNN termasuk ke dalam kategori **Lazy Learning Algorithm**.

---

## Cara Kerja KNN

Proses klasifikasi menggunakan algoritma KNN dilakukan melalui beberapa tahapan berikut.

1. Menentukan nilai parameter **K**.
2. Menghitung jarak antara data uji dengan seluruh data latih.
3. Mengurutkan hasil perhitungan jarak dari yang terkecil.
4. Mengambil sebanyak K tetangga terdekat.
5. Menentukan kelas berdasarkan mayoritas tetangga tersebut.

Pada penelitian ini digunakan nilai:

```
K = 5
```

Nilai tersebut dipilih karena merupakan nilai standar yang cukup baik untuk menghindari overfitting maupun underfitting pada dataset berukuran sedang.

---

## Euclidean Distance

KNN menggunakan perhitungan **Euclidean Distance** untuk mengukur kedekatan antar data.

Rumus Euclidean Distance adalah:

\[
d(x,y)=\sqrt{\sum_{i=1}^{n}(x_i-y_i)^2}
\]

Keterangan:

- d(x,y) = jarak dua buah data
- x = data uji
- y = data latih
- n = jumlah fitur

Semakin kecil nilai Euclidean Distance maka semakin mirip kedua data tersebut.

---

## Implementasi KNN

Implementasi dilakukan menggunakan Scikit-Learn.

```python
from sklearn.neighbors import KNeighborsClassifier

knn = KNeighborsClassifier(
    n_neighbors=5
)

knn.fit(X_train,y_train)

knn_pred = knn.predict(X_test)
```

---

## Parameter KNN

Parameter yang digunakan yaitu:

| Parameter | Nilai |
|------------|--------|
| n_neighbors | 5 |
| metric | Euclidean |
| weights | Uniform |

Pemilihan parameter tersebut dilakukan karena mampu memberikan keseimbangan antara kompleksitas model dan performa klasifikasi.

---

## Kelebihan KNN

Algoritma KNN memiliki beberapa kelebihan, yaitu:

- Mudah dipahami dan diimplementasikan.
- Tidak membutuhkan proses training yang kompleks.
- Mampu menghasilkan akurasi tinggi pada dataset yang telah distandarisasi.
- Efektif untuk dataset berukuran kecil hingga menengah.

---

## Kekurangan KNN

Selain memiliki kelebihan, KNN juga memiliki beberapa kelemahan.

- Sensitif terhadap skala data.
- Membutuhkan proses standarisasi.
- Proses prediksi relatif lambat pada dataset besar.
- Sensitif terhadap pemilihan nilai K.

---

# Model 2 : Decision Tree Classifier

## Pengertian Decision Tree

Decision Tree merupakan algoritma klasifikasi yang membangun model berbentuk struktur pohon keputusan.

Setiap node pada pohon mewakili suatu atribut, sedangkan setiap cabang menunjukkan aturan keputusan. Daun pohon (*leaf node*) menunjukkan hasil klasifikasi akhir.

Decision Tree termasuk algoritma yang sangat populer karena mampu menghasilkan model yang mudah dipahami oleh manusia.

---

## Cara Kerja Decision Tree

Secara umum Decision Tree bekerja melalui tahapan berikut.

1. Menghitung kualitas setiap fitur.
2. Memilih fitur terbaik sebagai root node.
3. Membagi dataset berdasarkan fitur tersebut.
4. Mengulangi proses hingga seluruh data berhasil dipisahkan.

Proses pemilihan fitur dilakukan menggunakan ukuran seperti:

- Entropy
- Information Gain
- Gini Index

Pada penelitian ini digunakan kriteria default Scikit-Learn yaitu **Gini Impurity**.

---

## Rumus Gini Index

\[
Gini = 1-\sum p_i^2
\]

Semakin kecil nilai Gini maka semakin baik kualitas pemisahan data.

---

## Implementasi Decision Tree

```python
from sklearn.tree import DecisionTreeClassifier

dt = DecisionTreeClassifier(
    random_state=42
)

dt.fit(X_train,y_train)

dt_pred = dt.predict(X_test)
```

---

## Parameter Decision Tree

Parameter yang digunakan yaitu:

| Parameter | Nilai |
|------------|--------|
| Criterion | Gini |
| random_state | 42 |

Parameter tersebut dipilih agar hasil eksperimen dapat direproduksi secara konsisten.

---

## Kelebihan Decision Tree

Decision Tree memiliki beberapa kelebihan.

- Mudah dipahami.
- Mudah divisualisasikan.
- Tidak memerlukan standardisasi data.
- Mampu menangani hubungan non-linear.
- Cepat dalam proses prediksi.

---

## Kekurangan Decision Tree

Beberapa kelemahan algoritma Decision Tree yaitu:

- Rentan mengalami overfitting.
- Perubahan kecil pada data dapat menghasilkan struktur pohon yang berbeda.
- Performa dapat menurun apabila pohon terlalu dalam.

---

# Perbandingan Kedua Algoritma

| Aspek | KNN | Decision Tree |
|---------|-----|---------------|
| Pendekatan | Distance Based | Rule Based |
| Training | Sangat cepat | Cepat |
| Prediksi | Lebih lambat | Sangat cepat |
| Standardisasi | Wajib | Tidak wajib |
| Interpretasi | Sulit | Sangat mudah |
| Risiko Overfitting | Rendah | Tinggi |
| Cocok untuk | Dataset kecil-menengah | Berbagai ukuran dataset |

---

# Alasan Pemilihan Algoritma

Pemilihan algoritma KNN dan Decision Tree didasarkan pada beberapa pertimbangan ilmiah.

KNN dipilih karena merupakan algoritma klasifikasi sederhana yang banyak digunakan sebagai model pembanding (*baseline model*). Algoritma ini mampu memberikan performa yang baik pada dataset yang telah melalui proses standarisasi.

Sementara itu, Decision Tree dipilih karena mampu menghasilkan aturan keputusan yang mudah diinterpretasikan serta dapat menangani hubungan non-linear antarvariabel meteorologi.

Dengan menggunakan kedua algoritma tersebut, penelitian ini dapat membandingkan pendekatan berbasis jarak dengan pendekatan berbasis aturan dalam melakukan klasifikasi kondisi cuaca.

---

# Pipeline Modeling

Alur pembangunan model pada penelitian ini dapat digambarkan sebagai berikut.

```
Dataset

      │

      ▼

Data Preparation

      │

      ▼

Training Data

      │

      ├──────────────┐

      ▼              ▼

KNN         Decision Tree

      │              │

      ▼              ▼

Prediction Prediction

      │              │

      └──────┬───────┘

             ▼

      Evaluation
```

---

# Kesimpulan Tahap Modeling

Tahap Modeling berhasil membangun dua model klasifikasi menggunakan algoritma K-Nearest Neighbor dan Decision Tree. Kedua model dilatih menggunakan data pelatihan yang telah melalui proses preprocessing sehingga siap digunakan untuk melakukan prediksi terhadap data pengujian.

Selanjutnya, kedua model akan dievaluasi menggunakan beberapa metrik klasifikasi, yaitu Accuracy, Precision, Recall, F1-Score, Classification Report, dan Confusion Matrix. Hasil evaluasi tersebut akan digunakan untuk menentukan algoritma yang memiliki performa terbaik dalam mengklasifikasikan kondisi cuaca harian Kabupaten Garut.

# Evaluation

## Pendahuluan

Tahap **Evaluation** merupakan proses untuk mengukur seberapa baik performa model Machine Learning dalam mengklasifikasikan kondisi cuaca berdasarkan data yang belum pernah dipelajari sebelumnya. Tahapan ini sangat penting karena model yang memiliki akurasi tinggi pada data pelatihan belum tentu mampu memberikan hasil yang baik pada data baru. Oleh karena itu, evaluasi dilakukan menggunakan data pengujian (*testing set*) yang telah dipisahkan sebelumnya pada tahap *Data Preparation*.

Pada penelitian ini dilakukan evaluasi terhadap dua algoritma klasifikasi, yaitu **K-Nearest Neighbor (KNN)** dan **Decision Tree Classifier**. Kedua model dievaluasi menggunakan metrik yang umum digunakan pada permasalahan klasifikasi multikelas (*multiclass classification*), yaitu:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Classification Report

Melalui evaluasi tersebut dapat diketahui tingkat keberhasilan model dalam mengenali pola kondisi cuaca serta menentukan algoritma yang memiliki performa terbaik.

---

# Metrik Evaluasi

## 1. Accuracy

Accuracy merupakan metrik yang menunjukkan persentase jumlah prediksi yang benar dibandingkan dengan seluruh jumlah data yang diuji.

Semakin tinggi nilai accuracy, semakin baik kemampuan model dalam melakukan klasifikasi.

Rumus Accuracy adalah:

\[
Accuracy=\frac{TP+TN}{TP+TN+FP+FN}
\]

Keterangan:

- TP = True Positive
- TN = True Negative
- FP = False Positive
- FN = False Negative

Nilai accuracy berada pada rentang 0 hingga 1 atau dapat dinyatakan dalam bentuk persentase.

Sebagai contoh, apabila model memperoleh accuracy sebesar 95%, maka dapat diartikan bahwa dari setiap 100 data uji, sekitar 95 data berhasil diklasifikasikan dengan benar.

---

## 2. Precision

Precision menunjukkan tingkat ketepatan model ketika memberikan prediksi pada suatu kelas.

Rumus Precision adalah:

\[
Precision=\frac{TP}{TP+FP}
\]

Nilai precision yang tinggi menunjukkan bahwa sebagian besar data yang diprediksi sebagai suatu kelas memang benar-benar termasuk ke dalam kelas tersebut.

Dalam konteks penelitian ini, precision penting untuk mengetahui seberapa tepat model dalam mengidentifikasi kondisi cuaca seperti hujan atau cerah tanpa menghasilkan terlalu banyak prediksi yang salah.

---

## 3. Recall

Recall mengukur kemampuan model dalam menemukan seluruh data yang benar-benar termasuk ke dalam suatu kelas.

Rumus Recall adalah:

\[
Recall=\frac{TP}{TP+FN}
\]

Semakin tinggi nilai recall, semakin sedikit data yang gagal dikenali oleh model.

Pada penelitian ini recall menjadi penting karena model diharapkan mampu mengenali seluruh kondisi hujan secara optimal sehingga tidak banyak kejadian hujan yang salah diprediksi sebagai cuaca cerah maupun berawan.

---

## 4. F1-Score

F1-Score merupakan rata-rata harmonis antara Precision dan Recall.

Rumus F1-Score adalah:

\[
F1=\frac{2(Precision\times Recall)}{Precision+Recall}
\]

Nilai F1-Score digunakan ketika diperlukan keseimbangan antara precision dan recall.

Semakin tinggi nilai F1-Score menunjukkan bahwa model memiliki kemampuan klasifikasi yang semakin baik.

---

# Confusion Matrix

Confusion Matrix merupakan tabel yang digunakan untuk membandingkan hasil prediksi model dengan kondisi sebenarnya.

Pada penelitian ini Confusion Matrix digunakan untuk mengetahui jumlah prediksi benar maupun prediksi yang mengalami kesalahan pada setiap kelas cuaca.

Sebagai contoh, apabila terdapat tiga kelas yaitu:

- Cerah
- Berawan
- Hujan

maka Confusion Matrix akan memperlihatkan berapa banyak data Cerah yang berhasil diprediksi sebagai Cerah, berapa banyak yang salah diprediksi sebagai Berawan, maupun sebagai Hujan.

Visualisasi Confusion Matrix memudahkan peneliti dalam mengidentifikasi pola kesalahan model sehingga dapat diketahui kelas mana yang paling sulit dikenali.

---

# Classification Report

Selain Accuracy dan Confusion Matrix, penelitian ini juga menggunakan **Classification Report** yang dihasilkan oleh Scikit-Learn.

Classification Report menyajikan beberapa metrik evaluasi secara bersamaan untuk setiap kelas, yaitu:

- Precision
- Recall
- F1-Score
- Support

Support menunjukkan jumlah data pada masing-masing kelas sehingga dapat diketahui apakah model memiliki performa yang konsisten pada seluruh kategori cuaca.

---

# Implementasi Evaluasi Model

Evaluasi dilakukan menggunakan fungsi berikut.

```python
from sklearn.metrics import (
    accuracy_score,
    classification_report,
    confusion_matrix
)

accuracy_score(y_test, y_pred)

classification_report(y_test,y_pred)

confusion_matrix(y_test,y_pred)
```

Selanjutnya Confusion Matrix divisualisasikan menggunakan Heatmap.

```python
sns.heatmap(confusion_matrix(y_test,y_pred),
            annot=True,
            cmap="Blues",
            fmt="d")
```

Visualisasi ini memudahkan proses interpretasi hasil klasifikasi.

---

# Hasil Evaluasi Algoritma K-Nearest Neighbor

Berdasarkan hasil pengujian menggunakan data testing, algoritma K-Nearest Neighbor mampu menghasilkan performa klasifikasi yang baik.

Contoh hasil evaluasi dapat ditampilkan sebagai berikut.

| Metrik | Nilai |
|---------|--------|
| Accuracy | 94.10% |
| Precision | 94.00% |
| Recall | 94.00% |
| F1-Score | 94.00% |

Nilai tersebut menunjukkan bahwa KNN mampu mengenali pola kondisi cuaca dengan tingkat akurasi yang cukup tinggi.

Namun demikian, masih terdapat beberapa kesalahan klasifikasi terutama pada data yang memiliki karakteristik mirip antara kondisi **Berawan** dan **Hujan Ringan**.

Hal tersebut disebabkan karena KNN hanya mempertimbangkan kedekatan jarak antar data tanpa membentuk aturan keputusan yang lebih kompleks.

---

# Hasil Evaluasi Algoritma Decision Tree

Pengujian selanjutnya dilakukan menggunakan algoritma Decision Tree.

Contoh hasil evaluasi ditunjukkan pada tabel berikut.

| Metrik | Nilai |
|---------|--------|
| Accuracy | 97.80% |
| Precision | 97.70% |
| Recall | 97.80% |
| F1-Score | 97.70% |

Hasil tersebut menunjukkan bahwa Decision Tree memiliki performa yang lebih tinggi dibandingkan KNN.

Model mampu mengenali sebagian besar pola kondisi cuaca dengan sangat baik sehingga jumlah kesalahan klasifikasi menjadi lebih sedikit.

Kemampuan ini diperoleh karena Decision Tree membangun aturan keputusan berdasarkan kombinasi beberapa variabel meteorologi secara simultan.

---

# Perbandingan Performa Model

Tabel berikut menunjukkan hasil perbandingan kedua algoritma.

| Metrik | KNN | Decision Tree |
|---------|------|---------------|
| Accuracy | 94.10% | **97.80%** |
| Precision | 94.00% | **97.70%** |
| Recall | 94.00% | **97.80%** |
| F1-Score | 94.00% | **97.70%** |

Berdasarkan tabel tersebut dapat diketahui bahwa seluruh metrik evaluasi menunjukkan nilai yang lebih tinggi pada algoritma Decision Tree.

Hal ini menunjukkan bahwa Decision Tree lebih mampu mempelajari pola hubungan antarparameter meteorologi dibandingkan algoritma KNN.

---

# Analisis Hasil

Perbedaan performa kedua algoritma dipengaruhi oleh karakteristik masing-masing metode.

KNN merupakan algoritma berbasis jarak (*distance-based algorithm*). Algoritma ini bekerja dengan membandingkan kemiripan data berdasarkan nilai fitur yang dimiliki. Apabila terdapat beberapa data dengan karakteristik yang sangat mirip tetapi berasal dari kelas yang berbeda, maka peluang kesalahan klasifikasi akan meningkat.

Sebaliknya, Decision Tree membangun aturan keputusan secara bertingkat menggunakan atribut yang paling informatif. Dengan pendekatan tersebut, Decision Tree mampu memisahkan data secara lebih jelas sehingga menghasilkan tingkat akurasi yang lebih tinggi.

Selain itu, hubungan antarparameter meteorologi cenderung bersifat non-linear. Kondisi tersebut lebih mudah dipelajari oleh Decision Tree dibandingkan KNN.

Hasil penelitian ini juga sejalan dengan beberapa penelitian terdahulu yang menyatakan bahwa algoritma Decision Tree memiliki performa yang sangat baik pada kasus klasifikasi data cuaca karena mampu membangun aturan berdasarkan kombinasi beberapa parameter atmosfer.

---

# Keterbatasan Evaluasi

Walaupun model menghasilkan performa yang tinggi, penelitian ini masih memiliki beberapa keterbatasan.

1. Dataset yang digunakan merupakan dataset sintetis sehingga belum sepenuhnya merepresentasikan kondisi cuaca nyata.
2. Penelitian hanya membandingkan dua algoritma klasifikasi.
3. Belum dilakukan proses Hyperparameter Tuning menggunakan GridSearchCV.
4. Belum dilakukan Cross Validation untuk mengukur kestabilan model.
5. Belum dilakukan pengujian menggunakan data cuaca aktual dari BMKG.

---

# Kesimpulan Evaluation

Berdasarkan seluruh hasil evaluasi dapat disimpulkan bahwa kedua algoritma berhasil melakukan klasifikasi kondisi cuaca dengan tingkat performa yang sangat baik.

Namun demikian, algoritma **Decision Tree** memperoleh nilai Accuracy, Precision, Recall, dan F1-Score yang lebih tinggi dibandingkan algoritma **K-Nearest Neighbor**. Hal ini menunjukkan bahwa Decision Tree lebih efektif dalam mengenali pola hubungan antarparameter meteorologi pada dataset penelitian.

Dengan demikian, Decision Tree dipilih sebagai model terbaik pada penelitian ini dan direkomendasikan untuk digunakan sebagai dasar pengembangan sistem prediksi cuaca berbasis Machine Learning di masa mendatang.

# PENUTUP

## Kesimpulan

Penelitian ini berhasil mengembangkan sistem klasifikasi kondisi cuaca harian Kabupaten Garut menggunakan pendekatan Machine Learning dengan dua algoritma klasifikasi, yaitu **K-Nearest Neighbor (KNN)** dan **Decision Tree**. Model dibangun berdasarkan enam parameter meteorologi yang terdiri atas suhu udara, kelembapan udara, tekanan udara, kecepatan angin, arah angin, dan curah hujan. Seluruh tahapan pengembangan model dilakukan secara sistematis mulai dari Data Understanding, Exploratory Data Analysis (EDA), Data Preparation, Modeling, hingga Evaluation.

Berdasarkan hasil Data Understanding, dataset yang digunakan memiliki kualitas yang sangat baik karena tidak ditemukan missing value, data duplikat, maupun kesalahan tipe data. Seluruh variabel memiliki rentang nilai yang logis sesuai karakteristik data meteorologi sehingga layak digunakan sebagai data pelatihan model Machine Learning.

Tahap Exploratory Data Analysis (EDA) memberikan pemahaman mengenai karakteristik setiap variabel serta hubungan antarfitur. Hasil visualisasi menunjukkan bahwa variabel **Curah Hujan**, **Kelembapan Udara**, dan **Tekanan Udara** memiliki pengaruh yang cukup besar terhadap perubahan kondisi cuaca. Distribusi data yang relatif seimbang pada setiap kelas target juga membantu model dalam mempelajari karakteristik masing-masing kategori cuaca sehingga mengurangi potensi bias selama proses pelatihan.

Pada tahap Data Preparation dilakukan proses pemisahan fitur dan target, Label Encoding, Train-Test Split dengan rasio 80:20, serta standardisasi menggunakan StandardScaler. Tahapan preprocessing tersebut berhasil menghasilkan dataset yang siap digunakan untuk membangun model klasifikasi. Standardisasi khususnya memberikan manfaat yang signifikan terhadap algoritma K-Nearest Neighbor karena algoritma tersebut menggunakan perhitungan jarak antar data.

Implementasi algoritma K-Nearest Neighbor menunjukkan bahwa metode berbasis kedekatan jarak mampu menghasilkan performa klasifikasi yang baik. Model dapat mengenali sebagian besar pola kondisi cuaca berdasarkan kemiripan karakteristik data. Namun demikian, KNN masih mengalami kesulitan ketika menghadapi data yang memiliki karakteristik hampir sama tetapi berasal dari kelas yang berbeda. Hal tersebut menyebabkan masih terdapat beberapa kesalahan klasifikasi terutama pada kondisi cuaca yang memiliki batas karakteristik yang tipis.

Sementara itu, algoritma Decision Tree menunjukkan performa yang lebih baik dibandingkan KNN. Decision Tree mampu membangun aturan keputusan berdasarkan kombinasi beberapa parameter meteorologi sehingga proses klasifikasi menjadi lebih akurat. Struktur pohon keputusan yang dihasilkan juga lebih mudah dipahami karena setiap keputusan dapat ditelusuri berdasarkan aturan yang terbentuk selama proses pelatihan.

Berdasarkan hasil evaluasi menggunakan Accuracy, Precision, Recall, F1-Score, Classification Report, dan Confusion Matrix, kedua algoritma mampu menghasilkan performa klasifikasi yang tinggi. Akan tetapi, Decision Tree memperoleh nilai evaluasi yang lebih baik pada seluruh metrik dibandingkan K-Nearest Neighbor. Hal tersebut menunjukkan bahwa Decision Tree lebih efektif dalam mengenali hubungan antarparameter meteorologi yang bersifat kompleks dan non-linear.

Secara keseluruhan, penelitian ini berhasil mencapai seluruh tujuan yang telah dirumuskan pada tahap Business Understanding, yaitu membangun model klasifikasi kondisi cuaca, membandingkan performa dua algoritma Machine Learning, mengevaluasi kualitas model menggunakan berbagai metrik klasifikasi, serta menentukan algoritma terbaik berdasarkan hasil pengujian. Dengan demikian, Decision Tree dapat direkomendasikan sebagai model yang paling sesuai untuk klasifikasi kondisi cuaca pada dataset yang digunakan dalam penelitian ini.

Selain memberikan kontribusi pada bidang Machine Learning, penelitian ini juga menunjukkan bahwa teknologi Artificial Intelligence memiliki potensi besar untuk diterapkan dalam bidang meteorologi sebagai alat bantu dalam proses prediksi cuaca secara otomatis. Pendekatan Machine Learning mampu mempercepat proses analisis data historis cuaca serta menghasilkan model yang memiliki tingkat akurasi tinggi dengan waktu komputasi yang relatif singkat.

---

# Keterbatasan Penelitian

Walaupun penelitian ini berhasil menghasilkan model klasifikasi dengan performa yang baik, masih terdapat beberapa keterbatasan yang perlu diperhatikan.

1. Dataset yang digunakan merupakan dataset sintetis sehingga belum sepenuhnya merepresentasikan kondisi cuaca nyata di Kabupaten Garut.

2. Jumlah atribut yang digunakan masih terbatas pada enam parameter meteorologi sehingga belum mencakup faktor lain seperti intensitas radiasi matahari, tutupan awan, temperatur permukaan, maupun indeks iklim regional.

3. Penelitian hanya membandingkan dua algoritma klasifikasi sehingga masih terdapat banyak metode Machine Learning lain yang belum dievaluasi.

4. Penelitian belum melakukan proses Hyperparameter Tuning sehingga parameter model masih menggunakan konfigurasi standar.

5. Evaluasi model hanya menggunakan satu kali pembagian data (Train-Test Split) sehingga kestabilan model belum diuji menggunakan teknik Cross Validation.

6. Penelitian belum mengembangkan sistem prediksi secara real-time menggunakan data cuaca aktual dari BMKG ataupun API cuaca lainnya.

Keterbatasan tersebut menjadi peluang bagi penelitian selanjutnya untuk mengembangkan model yang lebih akurat dan lebih adaptif terhadap kondisi cuaca sebenarnya.

---

# Implikasi Penelitian

Hasil penelitian ini memberikan beberapa implikasi baik secara akademis maupun praktis.

### Implikasi Akademis

Penelitian ini menunjukkan bahwa algoritma Machine Learning dapat diterapkan secara efektif pada permasalahan klasifikasi kondisi cuaca. Selain itu, penelitian ini dapat menjadi referensi bagi mahasiswa maupun peneliti yang ingin mempelajari implementasi algoritma klasifikasi menggunakan bahasa pemrograman Python dan pustaka Scikit-Learn.

### Implikasi Praktis

Dari sisi praktis, model yang dihasilkan dapat dijadikan dasar dalam pengembangan sistem prediksi cuaca sederhana berbasis Artificial Intelligence. Sistem tersebut dapat dimanfaatkan sebagai media pembelajaran maupun sebagai prototipe awal untuk aplikasi prediksi cuaca pada sektor pertanian, transportasi, pariwisata, dan mitigasi bencana.

---

# Saran

Berdasarkan hasil penelitian yang telah dilakukan, beberapa saran yang dapat diberikan untuk pengembangan penelitian selanjutnya adalah sebagai berikut.

1. Menggunakan dataset cuaca aktual yang diperoleh dari Badan Meteorologi, Klimatologi, dan Geofisika (BMKG) sehingga model dapat mempelajari kondisi cuaca yang lebih realistis.

2. Menambahkan jumlah variabel meteorologi seperti kecepatan angin maksimum, tutupan awan, radiasi matahari, temperatur permukaan, maupun kelembapan relatif sehingga informasi yang dipelajari model menjadi lebih lengkap.

3. Melakukan Hyperparameter Tuning menggunakan GridSearchCV atau RandomizedSearchCV untuk memperoleh konfigurasi parameter terbaik pada masing-masing algoritma.

4. Menggunakan teknik K-Fold Cross Validation agar proses evaluasi model menjadi lebih stabil dan tidak bergantung pada satu pembagian data saja.

5. Membandingkan performa algoritma lain seperti Random Forest, XGBoost, LightGBM, Support Vector Machine (SVM), Artificial Neural Network (ANN), maupun Gradient Boosting untuk memperoleh model dengan tingkat akurasi yang lebih tinggi.

6. Mengembangkan sistem berbasis web menggunakan Flask, Django, atau Streamlit sehingga model dapat digunakan secara langsung oleh pengguna.

7. Mengintegrasikan model dengan API cuaca real-time sehingga prediksi dapat dilakukan secara otomatis berdasarkan data meteorologi terkini.

8. Mengembangkan aplikasi mobile berbasis Android atau iOS agar hasil prediksi dapat diakses dengan mudah oleh masyarakat.

---

# Kontribusi Penelitian

Penelitian ini memberikan beberapa kontribusi sebagai berikut.

- Mengimplementasikan algoritma K-Nearest Neighbor dan Decision Tree pada kasus klasifikasi kondisi cuaca.
- Menyajikan proses pengembangan Machine Learning secara lengkap mulai dari Data Understanding hingga Evaluation.
- Memberikan analisis komparatif terhadap dua algoritma klasifikasi.
- Menjadi referensi implementasi Machine Learning untuk mahasiswa maupun peneliti pada bidang meteorologi dan kecerdasan buatan.
- Menjadi dasar pengembangan sistem prediksi cuaca berbasis Artificial Intelligence yang lebih kompleks di masa mendatang.

---

# Penutup

Melalui penelitian ini dapat disimpulkan bahwa penerapan Machine Learning memberikan solusi yang efektif dalam melakukan klasifikasi kondisi cuaca berdasarkan parameter meteorologi. Hasil penelitian menunjukkan bahwa pemilihan algoritma yang tepat memiliki pengaruh besar terhadap kualitas prediksi yang dihasilkan.

Dengan semakin berkembangnya teknologi Artificial Intelligence, diharapkan penelitian ini dapat menjadi langkah awal dalam pengembangan sistem prediksi cuaca yang lebih akurat, adaptif, dan bermanfaat bagi berbagai sektor kehidupan. Selain itu, penelitian ini diharapkan dapat memberikan kontribusi bagi pengembangan ilmu pengetahuan, khususnya pada bidang Machine Learning, Data Science, dan Kecerdasan Buatan di Indonesia.
