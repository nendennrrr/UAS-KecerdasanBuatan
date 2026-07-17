# Prediksi Kondisi Cuaca Menggunakan Algoritma K-Nearest Neighbor (KNN) dan Decision Tree

## Deskripsi Proyek
Proyek ini merupakan implementasi Machine Learning untuk melakukan klasifikasi kondisi cuaca berdasarkan parameter meteorologi. Penelitian ini membangun dan membandingkan dua algoritma klasifikasi yaitu K-Nearest Neighbor (KNN) dan Decision Tree.

## Latar Belakang
Cuaca memiliki pengaruh besar terhadap berbagai aktivitas manusia seperti pertanian, transportasi, pariwisata, dan mitigasi bencana. Perubahan kondisi atmosfer yang kompleks membuat prediksi cuaca menjadi tantangan penting.

Perkembangan Machine Learning memungkinkan komputer mempelajari pola dari data historis cuaca sehingga dapat menghasilkan prediksi secara otomatis. Penelitian ini menggunakan parameter suhu, kelembapan, tekanan udara, kecepatan angin, arah angin, dan curah hujan untuk mengklasifikasikan kondisi cuaca menjadi Cerah, Berawan, dan Hujan.

## Tujuan Penelitian
- Membangun model klasifikasi kondisi cuaca menggunakan Machine Learning.
- Membandingkan performa algoritma KNN dan Decision Tree.
- Mengevaluasi model menggunakan Accuracy, Precision, Recall, F1-Score, dan Confusion Matrix.
- Menentukan algoritma terbaik untuk klasifikasi kondisi cuaca.

## Dataset
Dataset yang digunakan merupakan dataset sintetis berjumlah 5.000 observasi yang dibuat untuk kebutuhan pembelajaran Machine Learning.

Dataset memiliki fitur:
| Kolom | Deskripsi |
|---|---|
| Suhu_C | Suhu udara (°C) |
| Kelembaban_Persen | Persentase kelembapan udara |
| Tekanan_Udara_hPa | Tekanan atmosfer (hPa) |
| Kecepatan_Angin_kmjam | Kecepatan angin (km/jam) |
| Arah_Angin_Derajat | Arah angin dalam derajat |
| Curah_Hujan_mm | Intensitas curah hujan (mm) |
| Kondisi_Cuaca | Label target (Cerah, Berawan, Hujan) |

## Metodologi
Penelitian dilakukan melalui tahapan:

### 1. Data Understanding
Melakukan pemeriksaan struktur data, tipe data, jumlah observasi, missing value, dan karakteristik dataset.

### 2. Exploratory Data Analysis (EDA)
Visualisasi yang digunakan:
- Histogram
- Boxplot
- Countplot
- Heatmap korelasi

### 3. Data Preparation
Tahapan preprocessing:
- Pemeriksaan missing value
- Pemisahan fitur dan target
- Label Encoding
- Train-Test Split
- Standardisasi menggunakan StandardScaler

## Modeling

### K-Nearest Neighbor (KNN)
KNN melakukan klasifikasi berdasarkan kedekatan data dengan sejumlah tetangga terdekat.

Kelebihan:
- Mudah dipahami.
- Implementasi sederhana.
- Tidak membutuhkan proses training kompleks.

Kekurangan:
- Sensitif terhadap skala data.
- Waktu prediksi lebih besar pada dataset besar.

### Decision Tree
Decision Tree membangun aturan keputusan berbentuk pohon berdasarkan fitur yang paling efektif dalam memisahkan kelas.

Kelebihan:
- Mudah diinterpretasikan.
- Cepat dalam prediksi.
- Dapat menangani pola kompleks.

Kekurangan:
- Berpotensi mengalami overfitting.

## Evaluasi Model
Evaluasi dilakukan menggunakan:
- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

## Library
Library Python yang digunakan:
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Struktur Folder
```text
.
├── dataset/
│   └── dataset_cuaca_garut_5000.csv
├── uas_model.ipynb
├── README.md
└── laporan_uas.md
```

## Cara Menjalankan Program

Install library:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook
```

Jalankan Jupyter Notebook:
```bash
jupyter notebook
```

Kemudian buka:
```
uas_model.ipynb
```

## Hasil Penelitian
Berdasarkan hasil pengujian, algoritma Decision Tree memberikan performa lebih baik dibandingkan KNN pada dataset yang digunakan. Decision Tree mampu mengenali pola hubungan antar variabel meteorologi dan menghasilkan klasifikasi kondisi cuaca dengan tingkat akurasi yang lebih tinggi.

## Pengembangan Selanjutnya
Pengembangan yang dapat dilakukan:
- Hyperparameter tuning menggunakan GridSearchCV.
- Cross Validation.
- Implementasi Random Forest, XGBoost, atau LightGBM.
- Menggunakan dataset cuaca aktual dari BMKG.
- Deployment menggunakan Flask atau Streamlit.
- Integrasi API cuaca real-time.

## Kesimpulan
Penelitian berhasil membangun model klasifikasi kondisi cuaca menggunakan algoritma KNN dan Decision Tree. Kedua algoritma mampu mempelajari pola data meteorologi, namun Decision Tree menjadi model terbaik berdasarkan hasil evaluasi performa.

## Referensi
1. Alzahrani, A., Alghamdi, A., Alghamdi, A., & Alshamrani, A. (2022). Deterministic Weather Forecasting Models Based on Intelligent Predictors: A Survey. *Journal of King Saud University – Computer and Information Sciences*. https://doi.org/10.1016/j.jksuci.2020.11.006

2. Bauer, P., Dueben, P. D., Hoefler, T., et al. (2022). ESA-ECMWF Report on Recent Progress and Research Directions in Machine Learning for Earth System Observation and Prediction. *npj Climate and Atmospheric Science, 5*(59). https://doi.org/10.1038/s41612-022-00269-z

3. Sharma, P., Kumar, R., & Singh, A. (2024). Comparative Analysis of Weather Prediction Using Classification Algorithm: Random Forest Classifier, Decision Tree Classifier and Extra Tree Classifier. *International Journal of Research Publication and Reviews*.

4. Sari, R., Pratama, A., & Nugroho, D. (2023). Implementasi Algoritma K-Nearest Neighbor untuk Klasifikasi Cuaca. *Jurnal Algoritme*.

5. Pedregosa, F., Varoquaux, G., Gramfort, A., Michel, V., Thirion, B., Grisel, O., Blondel, M., Prettenhofer, P., Weiss, R., Dubourg, V., Vanderplas, J., Passos, A., Cournapeau, D., Brucher, M., Perrot, M., & Duchesnay, É. (2011). Scikit-learn: Machine Learning in Python. *Journal of Machine Learning Research, 12*, 2825–2830.

## Penulis
**Nenden Nurdianti - 2406113**  
Program Studi Teknik Informatika  
Institut Teknologi Garut

## Lisensi
Proyek ini dibuat untuk memenuhi tugas Ujian Akhir Semester (UAS) Mata Kuliah Kecerdasan Buatan dan digunakan untuk keperluan akademik.
