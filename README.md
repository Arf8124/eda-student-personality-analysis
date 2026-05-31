# eda-student-personality-analysis
# Data Preprocessing Python Practice

Repositori ini berisi implementasi praktis tahap pra-pemrosesan data (*data preprocessing*) menggunakan Python. Proses ini merupakan langkah awal yang krusial dalam alur kerja data science untuk memastikan data bersih, konsisten, dan siap digunakan untuk tahap pemodelan machine learning.

## 📌 Deskripsi Proyek
Proyek ini melakukan eksplorasi dan pembersihan data pada dataset mahasiswa (`dataset_tugas1_preprocessing.csv`) yang memiliki beberapa masalah umum, seperti nilai yang hilang (*missing values*) serta format tipe data yang belum terstandarisasi.

### Informasi Dataset:
* **Jumlah Data:** 99 baris, 8 kolom
* **Fitur/Kolom:**
    * `ID`: Identitas unik mahasiswa (Object)
    * `Nama`: Nama mahasiswa (Object)
    * `Jenis_Kelamin`: Laki-laki / Perempuan (Object)
    * `Prodi`: Program studi mahasiswa (Object)
    * `Status`: Status akademis seperti Aktif, Lulus, Cuti, DO (Object)
    * `Nilai_Akhir`: Nilai indeks kategorikal A, B, C, D, E (Object)
    * `Tanggal_Ujian`: Tanggal pelaksanaan ujian (Object)
    * `Umur`: Umur mahasiswa (Float)

## 🛠️ Alur Pemrosesan Data (Pipeline)
### 1. Memuat Dataset (Load Dataset)
Membaca data eksternal berformat CSV ke dalam bentuk DataFrame menggunakan pustaka `pandas` serta menyiapkan lingkungan visualisasi.

### 2. Eksplorasi Data Awal (Exploratory Data Analysis - EDA)
* Memeriksa struktur dan tipe data setiap kolom menggunakan `.dtypes`.
* Mengidentifikasi persentase nilai yang hilang (*missing values*) pada dataset. Ditemukan adanya data kosong pada kolom `Nilai_Akhir` (29.29%) dan `Umur` (9.09%).
* Melihat statistik deskriptif data kategorikal maupun numerik menggunakan `.describe(include='all')`.

### 3. Penanganan Nilai Hilang (Handling Missing Values)
* **Fitur Kategorikal (`Nilai_Akhir`):** Mengisi nilai yang hilang (*imputation*) menggunakan nilai **Modus** (nilai yang paling sering muncul), yaitu kategori `'C'`.
* **Fitur Numerik (`Umur`):** Mengisi nilai yang hilang menggunakan nilai **Median** (nilai tengah), yaitu `23.0`, guna menghindari dampak dari pencilan (*outliers*).

## 🚀 Teknologi & Pustaka yang Digunakan
* **Python 3.8+**
* **Pandas:** Untuk manipulasi dan analisis struktur data data frame.
* **NumPy:** Untuk komputasi numerik.
* **Matplotlib:** Untuk keperluan visualisasi data/grafik (*backend* dikonfigurasi menggunakan `'Agg'`).
* **Scikit-Learn:** Menyediakan fungsi pembantu seperti `LabelEncoder` dan `train_test_split` untuk persiapan pemodelan tahap lanjut.

