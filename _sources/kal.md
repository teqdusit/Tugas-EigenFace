
---

# Komputasi Aljabar Linear

Universitas Trunojoyo Madura

## Pengertian

Komputasi Aljabar Linear (atau Computational Linear Algebra) adalah cabang ilmu yang menggabungkan matematika aljabar linear dengan ilmu komputer.Kalau di kelas matematika kita biasanya menghitung matriks ukuran $2 \times 2$ atau $3 \times 3$ menggunakan kertas dan pulpen, di dunia komputasi kita merancang algoritma agar komputer bisa menyelesaikan operasi matriks yang ukurannya sangat besar (bisa jutaan baris dan kolom) dengan cepat, akurat, dan efisien.Berikut adalah poin-poin penting untuk memahami apa itu komputasi aljabar linear:

### 1. Mengapa Kita Butuh Komputasi Aljabar Linear?
Komputer tidak melihat gambar, teks, atau suara seperti manusia. Komputer melihat semuanya sebagai angka.

- Gambar digital direpresentasikan sebagai matriks angka (intensitas warna piksel).

- Data mentah sering kali disusun dalam bentuk tabel besar (vektor dan matriks).

Ketika data tersebut harus diproses—misalnya memperjelas gambar atau memprediksi harga rumah—komputer harus melakukan operasi aljabar linear seperti perkalian matriks. Karena datanya sangat besar, kita tidak bisa asal menghitung; kita butuh metode komputasi yang efisien agar komputer tidak crash atau butuh waktu berhari-hari untuk selesai.

### 2. Operasi Utama dalam Komputasi Aljabar Linear
Ada beberapa operasi dasar yang paling sering dijinakkan oleh algoritma komputer:

- Sistem Persamaan Linear ($Ax = b$): Mencari nilai variabel yang tidak diketahui dari ribuan persamaan yang saling berhubungan.

- Dekomposisi Matriks (Faktorisasi): Memecah satu matriks besar menjadi beberapa matriks yang lebih sederhana (seperti $LU$, $QR$, atau Singular Value Decomposition / SVD). Ini mirip seperti memfaktorkan angka $12$ menjadi $3 \times 4$ agar lebih mudah dihitung.

- Eigenvalues dan Eigenvectors: Mencari arah dan faktor skala transformasi matriks, yang sangat penting untuk analisis struktur, fisika kuantum, hingga algoritma PageRank Google.

### 3. Tantangan Nyata dalam Komputasi

Membuat program untuk aljabar linear punya tantangan tersendiri dibanding menghitung manual:Keterbatasan Memori dan Matriks Jarang (Sparse Matrices)Jika kita punya matriks berukuran $100.000 \times 100.000$, menyimpannya secara mentah akan memakan memori komputer yang sangat besar. Untungnya, banyak matriks di dunia nyata yang sebagian besar elemennya adalah angka nol (disebut Sparse Matrix). Komputasi aljabar linear mempelajari bagaimana cara menyimpan dan menghitung angka-angka yang bukan nol saja untuk menghemat memori.Masalah Pembulatan (Floating-Point Error)Komputer memiliki batas ketelitian saat menyimpan angka desimal. Jika sebuah algoritma melakukan miliaran kali operasi perkalian dan pembagian, kesalahan kecil akibat pembulatan bisa menumpuk dan membuat hasil akhir menjadi sangat salah. Di sini kita mempelajari stabilitas numerik agar hasil hitungan komputer tetap akurat.

## Deskripsi

Website ini berisi dokumentasi tugas Komputasi Aljabar Linear yang meliputi:

- Persamaan Linear
- Eliminasi Gauss
- Matriks
- Determinan
- Transformasi Linear
- Eigen Value
- Singular Value Decomposition

## Peta Materi

```mermaid
graph TD

A[Aljabar Linear]

A --> B[Persamaan Linear]
A --> C[Matriks]
A --> D[Transformasi Linear]
A --> E[Eigen Value]

C --> F[Determinan]
C --> G[Invers]

E --> H[SVD]