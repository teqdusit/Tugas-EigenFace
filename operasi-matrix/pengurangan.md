# Pengurangan Matrix

## Pengertian 

Pengurangan matriks pada dasarnya memiliki konsep yang sangat mirip dengan penjumlahan matriks. Aturan mainnya tetap sama: kita hanya perlu mengurangkan elemen-elemen yang posisinya seletak (sejalan).
Berikut adalah penjelasan detail mengenai syarat, cara menghitung, dan contohnya.

## 1. Syarat Utama Pengurangan Matriks

Sama seperti penjumlahan, dua matriks atau lebih hanya bisa dikurangi jika memiliki ordo (ukuran) yang sama.
Artinya, jumlah baris dan jumlah kolom pada kedua matriks harus persis sama.
- Matriks $2 \times 2$ hanya bisa dikurangi dengan matriks $2 \times 2$.
- Matriks $3 \times 3$ hanya bisa dikurangi dengan matriks $3 \times 3$.
- Jika ordonya berbeda, maka matriks tersebut tidak dapat dikurangi.

## 2. Cara Menghitung

Misalkan kita memiliki dua matriks berukuran $2 \times 2$, yaitu matriks $A$ dan matriks $B$:

$$A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}, \quad B = \begin{pmatrix} e & f \\ g & h \end{pmatrix}$$

Untuk menguranginya, kita kurangkan elemen matriks pertama dengan elemen matriks kedua yang posisinya sama:

$$A - B = \begin{pmatrix} a-e & b-f \\ c-g & d-h \end{pmatrix}$$

## 3. Contoh Soal
Mari kita lihat contoh menggunakan angka. Diketahui:

$$A = \begin{pmatrix} 8 & 6 \\ 5 & 9 \end{pmatrix}, \quad B = \begin{pmatrix} 3 & 2 \\ 1 & 4 \end{pmatrix}$$

Langkah demi langkah penyelesaiannya:
1. Baris 1, Kolom 1: Kurangkan posisi kiri atas $\rightarrow 8 - 3 = 5$
2. Baris 1, Kolom 2: Kurangkan posisi kanan atas $\rightarrow 6 - 2 = 4$
3. Baris 2, Kolom 1: Kurangkan posisi kiri bawah $\rightarrow 5 - 1 = 4$
4. Baris 2, Kolom 2: Kurangkan posisi kanan bawah $\rightarrow 9 - 4 = 5$
Maka hasil akhirnya adalah:

$$A - B = \begin{pmatrix} 8-3 & 6-2 \\ 5-1 & 9-4 \end{pmatrix} = \begin{pmatrix} 5 & 4 \\ 4 & 5 \end{pmatrix}$$

Hati-hati dengan Bilangan Negatif!

Salah satu jebakan yang sering terjadi dalam pengurangan matriks adalah ketika elemen pada matriks kedua bernilai negatif. Kita harus mengingat aturan tanda matematika dasar: negatif bertemu negatif menjadi positif ($- \times - = +$).
Contoh:

$$\begin{pmatrix} 4 & 2 \\ 5 & -1 \end{pmatrix} - \begin{pmatrix} -2 & 3 \\ 1 & -5 \end{pmatrix}$$

1. Baris 1, Kolom 1: $4 - (-2) = 4 + 2 = 6$
2. Baris 1, Kolom 2: $2 - 3 = -1$
3. Baris 2, Kolom 1: $5 - 1 = 4$
4. Baris 2, Kolom 2: $-1 - (-5) = -1 + 5 = 4$
Hasil akhirnya:

$$\begin{pmatrix} 6 & -1 \\ 4 & 4 \end{pmatrix}$$

## 4. Sifat Pengurangan Matriks

Berbeda dengan penjumlahan, pengurangan matriks tidak bersifat komutatif. Artinya, jika kamu membalik urutan matriksnya, hasilnya akan berbeda (tandanya akan berubah menjadi kebalikannya):

$$A - B \neq B - A$$