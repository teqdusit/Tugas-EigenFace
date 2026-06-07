# Tugas Project - Eigen Face menggunakan Rumus SVD

## 1. Pengertian Eigen Face dan SVD

Apa itu EigenFace?

Eigenface adalah nama yang diberikan untuk sekumpulan vektor karakteristik (komponen utama) ketika teknik aljabar linear dan statistik diterapkan pada gambar wajah manusia. Secara visual, jika vektor karakteristik ini diubah kembali menjadi dimensi gambar 2D, mereka akan terlihat seperti wajah-wajah samar yang abstrak atau menyerupai hantu. Kumpulan "wajah hantu" inilah yang merepresentasikan fitur-fitur pembeda utama (seperti garis rahang, bayangan mata, atau bentuk hidung) antar-wajah yang ada di dalam dataset.

Mengapa Menggunakan Rumus SVD?

Singular Value Decomposition (SVD) adalah metode faktorisasi matriks yang memecah sebuah matriks data menjadi tiga matriks komponen utama. Dalam studi pengenalan wajah, SVD digunakan sebagai alat komputasi untuk melakukan PCA (Principal Component Analysis). Dibandingkan menghitung matriks kovarians yang ukurannya sangat besar dan membebani memori komputer, SVD mampu mengekstraksi komponen utama (Eigenface) langsung dari matriks data wajah asli secara jauh lebih cepat dan efisien.

## 2. Rumus Matematika SVD pada Data Wajah

Misalkan kita memiliki dataset berisi $M$ buah foto wajah, di mana setiap foto telah diubah menjadi satu vektor kolom panjang berukuran $N$ (total piksel). Seluruh vektor ini digabungkan membentuk sebuah matriks data wajah $A$ berukuran $N \times M$.Rumus utama SVD memfaktorkan matriks $A$ menjadi:
$A = U \cdot \Sigma \cdot V^T$
Detail Komponen Matriks:
1. Matriks $U$ (Left Singular Vectors) $\rightarrow$ Ukuran $N \times N$
- Kolom-kolom di dalam matriks $U$ bersifat saling tegak lurus (ortogonal).
- Di sinilah letak Eigenfaces. Kolom-kolom pertama pada matriks $U$ menyimpan informasi variasi wajah terbesar. Jika kolom ini di-reshape kembali ke ukuran gambar asli, kita mendapatkan visualisasi Eigenface.

2. Matriks $\Sigma$ (Singular Values) $\rightarrow$ Ukuran $N \times M$
- Merupakan matriks diagonal yang berisi nilai penyimpangan (singular values) yang diurutkan dari terbesar ke terkecil.
- Nilai ini melambangkan tingkat kepentingan atau "bobot" informasi dari setiap Eigenface yang bersesuaian di matriks $U$. Nilai yang kecil melambangkan noise atau detail tidak penting yang dapat dibuang (Reduksi Dimensi).

3. Matriks $V^T$ (Right Singular Vectors) $\rightarrow$ Ukuran $M \times M$
- Merepresentasikan koefisien atau kontribusi setiap foto wajah asli terhadap komponen ruang Eigenface yang terbentuk.

## 3. Alur Kerja 

Untuk mengimplementasikan teori di atas ke dalam kode program (misalnya menggunakan Python), berikut adalah tahapan logis atau algoritma yang dijalankan oleh sistem:

Tahap 1: Pra-proses Data Gambar (Preprocessing)
1. Load Gambar: Membaca semua gambar wajah dari dataset dan mengubahnya menjadi format grayscale (hitam putih).
2. Flattening: Mengubah setiap gambar matriks 2D menjadi satu vektor baris atau kolom 1D.
3. Matriks Data: Menggabungkan semua vektor gambar tersebut ke dalam satu matriks besar $A$.
4. Normalisasi (Wajah Rata-rata): * Hitung rata-rata dari seluruh wajah ($\Psi$).
- Kurangi setiap vektor wajah asli dengan wajah rata-rata ini ($\Phi_i = X_i - \Psi$). Langkah ini memastikan kita hanya fokus pada perbedaan antar-wajah.

Tahap 2: Menghitung SVD & Reduksi Dimensi
1. Masukkan matriks perbedaan wajah yang sudah dinormalisasi ke dalam fungsi SVD untuk mendapatkan matriks $ U $ , $ \Sigma $ , dan $ V^T $ .
2. Memilih $k$ Komponen Utama: Kita tidak perlu menggunakan semua kolom $ U $ . Pilih sejumlah $k$ kolom pertama (misal 10 atau 20) yang memiliki nilai singular terbesar di matriks  $ \Sigma $ . Matriks pangkas ini kita sebut sebagai Ruang Eigenface.

Tahap 3: Proyeksi Data (Training)
1. Proyeksikan semua gambar wajah dari database ke dalam Ruang Eigenface yang telah dipangkas.
2. Hasil proyeksi ini berupa vektor bobot (weight vector) berukuran kecil yang bertindak sebagai "sidik jari" digital untuk masing-masing wajah di database.

Tahap 4: Pengenalan Wajah Baru (Testing)
1. Masukkan foto wajah baru yang ingin diuji, ubah menjadi vektor, lalu kurangi dengan wajah rata-rata ( $ \Psi $ ) yang didapat pada Tahap 1.
2. Proyeksikan vektor wajah baru tersebut ke Ruang Eigenface untuk mendapatkan vektor bobotnya sendiri.
3. Klasifikasi Jarak: Hitung jarak terdekat (misalnya menggunakan rumus Euclidean Distance) antara vektor bobot wajah baru dengan seluruh vektor bobot wajah yang ada di database.
4. Jika jarak terkecil berada di bawah ambang batas (threshold) tertentu, maka sistem akan menampilkan identitas wajah yang paling cocok tersebut.

## 4. Cara menjalankan Program

Berikut adalah langkah-langkah menjalankan program di Google Colab:

1. Cara Menjalankan Kode di dalam Cell (Kotak Kode)
Google Colab menggunakan sistem berbasis Notebook (file .ipynb). Kode program kamu ditulis di dalam kotak-kotak yang disebut Cell. 
- Menggunakan Tombol Play: Di sebelah kiri setiap kotak kode, ada tombol berbentuk segitiga/Play dalam lingkaran. Cukup klik tombol tersebut untuk menjalankan kode di kotak itu.
- Menggunakan Shortcut Keyboard: Klik kotak kodenya, lalu tekan tombol Shift + Enter atau Ctrl + Enter di keyboard kamu.
  - Ctrl + Enter: Menjalankan kode dan tetap berada di kotak yang sama.
  - Shift + Enter: Menjalankan kode dan otomatis berpindah ke kotak di bawahnya.

2. Cara Mengunggah (Upload) Folder atau File Data
- Lihat di bilah menu sebelah kiri layar Colab.
- Klik ikon berbentuk Folder (paling bawah).
- (drag & drop) file gambar atau folder dataset dari laptop ke dalam area folder tersebut, atau klik ikon Upload (kertas dengan panah ke atas).

## 5. link collab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1e2xJwZ8vghJKkQnf5-Lr2vYDt1j5-XPt)



