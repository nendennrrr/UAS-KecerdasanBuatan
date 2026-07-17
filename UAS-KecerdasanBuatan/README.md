# Prediksi Cuaca Harian Kabupaten Garut Menggunakan Algoritma K-Nearest Neighbor (KNN) dan Decision Tree

## Deskripsi Proyek

Proyek ini merupakan implementasi teknik **Machine Learning** untuk melakukan klasifikasi kondisi cuaca harian di Kabupaten Garut berdasarkan sejumlah parameter meteorologi. Penelitian ini membangun dua model klasifikasi, yaitu **K-Nearest Neighbor (KNN)** dan **Decision Tree**, kemudian membandingkan performa kedua algoritma tersebut menggunakan berbagai metrik evaluasi.

Pengembangan proyek ini bertujuan untuk memberikan gambaran bagaimana algoritma pembelajaran mesin mampu mengenali pola dari data cuaca historis sehingga dapat digunakan sebagai sistem pendukung dalam proses prediksi kondisi cuaca. Hasil penelitian diharapkan dapat menjadi referensi dalam pengembangan sistem prediksi cuaca berbasis Artificial Intelligence yang lebih kompleks pada penelitian selanjutnya.

---

# Latar Belakang

Perubahan kondisi cuaca merupakan fenomena alam yang sangat dinamis dan dipengaruhi oleh berbagai faktor atmosfer. Informasi mengenai kondisi cuaca memiliki peranan penting dalam berbagai sektor kehidupan, seperti pertanian, transportasi, perikanan, pariwisata, hingga mitigasi bencana alam.

Di Indonesia, khususnya Kabupaten Garut, perubahan cuaca sering terjadi dalam waktu yang relatif singkat sehingga diperlukan metode yang mampu membantu proses prediksi secara cepat dan akurat. Selama ini prediksi cuaca umumnya dilakukan menggunakan pendekatan meteorologi numerik yang membutuhkan sumber daya komputasi besar serta data observasi yang kompleks.

Seiring berkembangnya bidang **Artificial Intelligence (AI)** dan **Machine Learning (ML)**, proses prediksi dapat dilakukan dengan memanfaatkan pola yang dipelajari dari data historis. Machine Learning memungkinkan komputer mengenali hubungan antar variabel meteorologi tanpa harus diprogram menggunakan aturan yang eksplisit.

Pada penelitian ini digunakan enam parameter cuaca, yaitu:

* Suhu udara
* Kelembapan udara
* Tekanan udara
* Kecepatan angin
* Arah angin
* Curah hujan

Parameter-parameter tersebut digunakan untuk mengklasifikasikan kondisi cuaca ke dalam tiga kategori utama, yaitu:

* Cerah
* Berawan
* Hujan

Penelitian ini juga bertujuan mengetahui algoritma klasifikasi mana yang memberikan performa terbaik antara **K-Nearest Neighbor (KNN)** dan **Decision Tree**.

---

# Tujuan Penelitian

Penelitian ini memiliki beberapa tujuan utama sebagai berikut.

1. Membangun model klasifikasi kondisi cuaca menggunakan algoritma Machine Learning.
2. Mengimplementasikan algoritma **K-Nearest Neighbor (KNN)**.
3. Mengimplementasikan algoritma **Decision Tree**.
4. Membandingkan performa kedua algoritma berdasarkan hasil evaluasi.
5. Mengukur kualitas model menggunakan Accuracy, Precision, Recall, F1-Score, dan Confusion Matrix.
6. Menentukan algoritma yang paling efektif dalam melakukan klasifikasi kondisi cuaca pada dataset yang digunakan.
7. Memberikan gambaran penerapan Machine Learning dalam bidang prediksi cuaca.

---

# Dataset

Dataset yang digunakan merupakan **dataset sintetis** yang disusun khusus untuk kebutuhan pembelajaran Machine Learning dan simulasi penelitian klasifikasi cuaca.

Jumlah data yang digunakan sebanyak **5.000 observasi** dengan tujuh atribut yang terdiri atas enam variabel independen dan satu variabel target.

| Kolom                 | Deskripsi                           |
| --------------------- | ----------------------------------- |
| Suhu_C                | Suhu udara dalam derajat Celcius    |
| Kelembaban_Persen     | Persentase kelembapan udara         |
| Tekanan_Udara_hPa     | Tekanan atmosfer dalam satuan hPa   |
| Kecepatan_Angin_kmjam | Kecepatan angin (km/jam)            |
| Arah_Angin_Derajat    | Arah datangnya angin (0–360°)       |
| Curah_Hujan_mm        | Intensitas curah hujan (mm)         |
| Kondisi_Cuaca         | Label kelas (Cerah, Berawan, Hujan) |

Seluruh data disusun sehingga memiliki distribusi yang menyerupai kondisi meteorologi nyata untuk kebutuhan eksperimen klasifikasi.

---

# Metodologi Penelitian

Tahapan penelitian mengikuti alur standar dalam pengembangan model Machine Learning.

## 1. Data Understanding

Tahapan awal dilakukan untuk memahami karakteristik dataset yang digunakan. Proses ini meliputi:

* Melihat ukuran dataset
* Menampilkan beberapa data pertama
* Mengecek tipe data setiap atribut
* Mengidentifikasi missing value
* Menghitung statistik deskriptif
* Melihat distribusi setiap kelas target

Tahapan ini bertujuan memastikan kualitas data sebelum dilakukan proses pemodelan.

---

## 2. Exploratory Data Analysis (EDA)

EDA dilakukan untuk memahami hubungan antarvariabel serta distribusi data.

Visualisasi yang digunakan antara lain:

* Histogram distribusi seluruh fitur
* Boxplot untuk mendeteksi outlier
* Countplot distribusi kelas
* Heatmap korelasi antar fitur
* Pairplot (opsional)
* Scatter plot beberapa fitur penting

Melalui EDA dapat diketahui pola awal yang terdapat pada dataset.

---

## 3. Data Preparation

Sebelum proses pelatihan model dilakukan beberapa tahapan preprocessing.

### Pemeriksaan Missing Value

Memastikan seluruh data lengkap sehingga tidak memengaruhi hasil pelatihan model.

### Pemisahan Fitur dan Target

Dataset dipisahkan menjadi:

* Variabel independen (X)
* Variabel target (y)

### Label Encoding

Karena target berbentuk kategori, maka dilakukan proses Label Encoding sehingga dapat diproses oleh algoritma Machine Learning.

Contoh hasil encoding:

* Cerah → 0
* Berawan → 1
* Hujan → 2

### Train-Test Split

Dataset dibagi menjadi:

* 80% Data Training
* 20% Data Testing

Pembagian ini bertujuan menguji kemampuan generalisasi model terhadap data yang belum pernah dipelajari.

### Standardisasi Data

Karena algoritma KNN sangat sensitif terhadap skala data, seluruh fitur dinormalisasi menggunakan **StandardScaler** sehingga memiliki rata-rata 0 dan standar deviasi 1.

---

# Modeling

## K-Nearest Neighbor (KNN)

K-Nearest Neighbor merupakan algoritma klasifikasi berbasis kemiripan data.

Prinsip kerja KNN adalah mencari sejumlah tetangga terdekat (K) berdasarkan jarak Euclidean, kemudian menentukan kelas berdasarkan mayoritas tetangga tersebut.

### Kelebihan

* Mudah dipahami.
* Implementasi sederhana.
* Tidak membutuhkan proses training yang kompleks.
* Efektif pada dataset berukuran kecil hingga menengah.

### Kekurangan

* Sensitif terhadap skala data.
* Waktu prediksi relatif lambat pada dataset besar.
* Pemilihan nilai K sangat memengaruhi performa.

---

## Decision Tree

Decision Tree merupakan algoritma klasifikasi yang membangun struktur pohon keputusan berdasarkan atribut yang memberikan informasi terbaik dalam memisahkan kelas.

Algoritma memilih atribut menggunakan ukuran seperti **Gini Index** atau **Entropy**, kemudian membentuk aturan keputusan hingga seluruh data berhasil dipisahkan.

### Kelebihan

* Mudah dipahami dan diinterpretasikan.
* Cepat dalam proses prediksi.
* Dapat menangani hubungan non-linear antar variabel.
* Tidak memerlukan standardisasi data.

### Kekurangan

* Rentan mengalami overfitting.
* Perubahan kecil pada data dapat menghasilkan struktur pohon yang berbeda.

---

# Evaluasi Model

Untuk mengukur performa model digunakan beberapa metrik evaluasi klasifikasi.

## Accuracy

Mengukur persentase prediksi yang benar terhadap seluruh data pengujian.

## Precision

Mengukur ketepatan model dalam memberikan prediksi suatu kelas.

## Recall

Mengukur kemampuan model menemukan seluruh data yang benar pada suatu kelas.

## F1-Score

Merupakan rata-rata harmonik antara Precision dan Recall sehingga memberikan ukuran performa yang lebih seimbang.

## Confusion Matrix

Confusion Matrix digunakan untuk melihat jumlah prediksi benar maupun salah pada masing-masing kelas sehingga memberikan gambaran performa model secara lebih rinci.

---

# Library yang Digunakan

Penelitian ini dikembangkan menggunakan bahasa pemrograman **Python** dengan beberapa pustaka utama berikut.

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

Seluruh library digunakan untuk proses pengolahan data, visualisasi, pelatihan model, hingga evaluasi hasil klasifikasi.

---

# Struktur Folder

```text
.
├── dataset/
│   └── dataset_cuaca_garut_5000.csv
├── uas_model.ipynb
├── README.md
└── laporan_uas.md
```

Keterangan:

* **dataset/** menyimpan dataset penelitian.
* **uas_model.ipynb** berisi seluruh proses Machine Learning.
* **README.md** merupakan dokumentasi proyek.
* **laporan_uas.md** merupakan laporan penelitian.

---

# Cara Menjalankan Program

## 1. Clone Repository

```bash
git clone https://github.com/username/prediksi-cuaca-knn-decision-tree.git
```

Masuk ke folder proyek:

```bash
cd prediksi-cuaca-knn-decision-tree
```

---

## 2. Install Library

```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook
```

---

## 3. Jalankan Jupyter Notebook

```bash
jupyter notebook
```

Kemudian buka file:

```text
uas_model.ipynb
```

Seluruh tahapan penelitian dapat dijalankan secara berurutan mulai dari Data Understanding hingga Evaluasi Model.

---

# Hasil Penelitian

Berdasarkan hasil eksperimen yang dilakukan terhadap dataset cuaca sintetis, kedua algoritma berhasil mempelajari pola hubungan antar parameter meteorologi dan mampu melakukan klasifikasi kondisi cuaca dengan baik.

Namun demikian, algoritma **Decision Tree** menunjukkan performa yang lebih unggul dibandingkan **K-Nearest Neighbor**. Hal ini terlihat dari nilai Accuracy, Precision, Recall, dan F1-Score yang lebih tinggi pada data pengujian.

Decision Tree juga mampu membangun aturan keputusan yang mudah dipahami sehingga memberikan interpretasi yang lebih baik terhadap hubungan antar variabel cuaca.

Sementara itu, algoritma KNN tetap menunjukkan performa yang baik, namun lebih dipengaruhi oleh proses standardisasi data dan pemilihan jumlah tetangga (nilai K).

---

# Pengembangan Selanjutnya

Penelitian ini masih memiliki berbagai peluang pengembangan, antara lain:

* Melakukan Hyperparameter Tuning menggunakan GridSearchCV.
* Menggunakan K-Fold Cross Validation.
* Mengimplementasikan Random Forest.
* Mengimplementasikan XGBoost.
* Mengimplementasikan LightGBM.
* Menggunakan dataset cuaca aktual dari BMKG.
* Mengembangkan sistem prediksi berbasis Flask.
* Mengembangkan dashboard menggunakan Streamlit.
* Mengintegrasikan API cuaca real-time.
* Melakukan deployment pada layanan cloud agar dapat digunakan secara daring.

---

# Kesimpulan

Penelitian ini berhasil mengimplementasikan algoritma **K-Nearest Neighbor (KNN)** dan **Decision Tree** untuk melakukan klasifikasi kondisi cuaca berdasarkan parameter meteorologi. Kedua algoritma mampu mempelajari pola dari data historis dan menghasilkan prediksi kondisi cuaca secara otomatis.

Hasil evaluasi menunjukkan bahwa **Decision Tree** memberikan performa yang lebih baik dibandingkan KNN pada dataset yang digunakan. Selain menghasilkan tingkat akurasi yang tinggi, Decision Tree juga memiliki keunggulan dalam hal interpretasi model sehingga lebih mudah digunakan sebagai dasar pengambilan keputusan.

Secara keseluruhan, penelitian ini membuktikan bahwa pendekatan Machine Learning dapat dimanfaatkan sebagai alternatif dalam pengembangan sistem prediksi cuaca yang cepat, efisien, dan mudah diimplementasikan.

---

# Referensi

1. Alzahrani, A., Alghamdi, A., Alghamdi, A., & Alshamrani, A. (2022). *Deterministic Weather Forecasting Models Based on Intelligent Predictors: A Survey*. Journal of King Saud University – Computer and Information Sciences.

2. Bauer, P., Dueben, P. D., Hoefler, T., et al. (2022). *ESA-ECMWF Report on Recent Progress and Research Directions in Machine Learning for Earth System Observation and Prediction*. npj Climate and Atmospheric Science, 5(59).

3. Sharma, P., Kumar, R., & Singh, A. (2024). *Comparative Analysis of Weather Prediction Using Classification Algorithm: Random Forest Classifier, Decision Tree Classifier and Extra Tree Classifier*. International Journal of Research Publication and Reviews.

4. Sari, R., Pratama, A., & Nugroho, D. (2023). *Implementasi Algoritma K-Nearest Neighbor untuk Klasifikasi Cuaca*. Jurnal Algoritme.

5. Pedregosa, F., et al. (2011). *Scikit-learn: Machine Learning in Python*. Journal of Machine Learning Research, 12, 2825–2830.

---

# Penulis

**Nenden Nurdianti**
**NIM:** 2406113
Program Studi Teknik Informatika
Institut Teknologi Garut

---

# Lisensi

Proyek ini disusun sebagai salah satu syarat untuk memenuhi **Ujian Akhir Semester (UAS)** Mata Kuliah **Kecerdasan Buatan** pada Program Studi Teknik Informatika, Institut Teknologi Garut.

Seluruh kode program, dokumentasi, serta dataset sintetis dalam repositori ini digunakan untuk keperluan pembelajaran dan penelitian akademik. Penggunaan kembali sebagian maupun seluruh isi proyek diperbolehkan untuk tujuan pendidikan dengan tetap mencantumkan sumber dan penulis.
