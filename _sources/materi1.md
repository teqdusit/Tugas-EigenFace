# Tugas Project - Eigen Face menggunakan Rumus SVD

## Pengertian

EigenFace adalah metode pengenalan wajah yang menggunakan teknik Principal Component Analysis (PCA) untuk mengekstraksi ciri-ciri penting dari citra wajah. Metode ini mengubah gambar wajah menjadi sekumpulan vektor fitur yang disebut eigenface, sehingga proses pengenalan wajah dapat dilakukan dengan lebih efisien. Singular Value Decomposition (SVD) adalah teknik dekomposisi matriks yang digunakan untuk memecah suatu matriks menjadi tiga matriks penyusun. Pada metode EigenFace, SVD digunakan untuk memperoleh eigenvector dan eigenvalue yang menjadi dasar pembentukan eigenface.

## Rumus SVD

$$
A = U \Sigma V^T
$$

A = matriks data wajah
Σ (Sigma) = matriks diagonal yang berisi singular value
Vᵀ = tranpose dari matriks vektor singular kanan

## Tujuan

membuat sistem pengenalan wajah menggunakan metode EigenFace dengan simular Value Decomposition (SVD).

## Langkah Algoritma 


1. Membaca seluruh citra training.
2. Mengubah citra menjadi grayscale.
3. Menghitung mean face.
4. Mengurangi setiap citra dengan mean face.
5. Melakukan dekomposisi SVD menggunakan rumus diatas
6. Mengambil beberapa eigenface dari matriks U.
7. Memproyeksikan wajah ke ruang eigenface.
8. Menghitung jarak Euclidean untuk menentukan wajah yang paling mirip.

## Implementasi program

Kode lengkap dapat diakses pada:

[Google Drive](https://colab.research.google.com/drive/1e2xJwZ8vghJKkQnf5-Lr2vYDt1j5-XPt#scrollTo=zx2xecH0H0ip)

## Hasil pengujian

Pada pengujian, sistem berhasil mengenali wajah Jokowi sebagai wajah yang paling mirip dengan nilai distance 0.0.

## Pengertian

Metode EigenFace menggunakan SVD dapat digunakan untuk mengenali wajah dengan cara mereduksi dimensi data citra dan membandingkan representasi fitur pada ruang eigenface.
