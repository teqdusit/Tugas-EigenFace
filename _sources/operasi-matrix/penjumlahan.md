# Penjumlahan Matrix

## Pengertian 

Penjumlahan matriks adalah salah satu operasi dasar dalam aljabar linear yang digunakan untuk menggabungkan dua matriks atau lebih. Konsepnya cukup sederhana: kita hanya perlu menjumlahkan elemen-elemen yang posisinya sejalan (seletak)

## Syarat Utama Penjumlahan Matriks

Dua matriks atau lebih hanya bisa dijumlahkan jika memiliki ordo (ukuran) yang sama.
Artinya, jumlah baris dan jumlah kolom pada matriks pertama harus persis sama dengan jumlah baris dan jumlah kolom pada matriks kedua.
- Matriks $2 \times 2$ hanya bisa dijumlahkan dengan matriks $2 \times 2$.
- Matriks $3 \times 2$ hanya bisa dijumlahkan dengan matriks $3 \times 2$.
- Jika ukurannya berbeda (misalnya matriks $2 \times 2$ ditambah matriks $3 \times 2$), maka matriks tersebut tidak dapat dijumlahkan.

## Cara Menghitung

Misalkan kita memiliki dua matriks berukuran $2 \times 2$, yaitu matriks $A$ dan matriks $B$:

$$A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}, \quad B = \begin{pmatrix} e & f \\ g & h \end{pmatrix}$$

Untuk menjumlahkannya, kita pasangkan elemen pada baris dan kolom yang sama:

$$A + B = \begin{pmatrix} a+e & b+f \\ c+g & d+h \end{pmatrix}$$

## Contoh Soal

Mari kita coba dengan angka. Diketahui dua matriks berikut:

$$A = \begin{pmatrix} 2 & 4 \\ 1 & 3 \end{pmatrix}, \quad B = \begin{pmatrix} 5 & 1 \\ 7 & 2 \end{pmatrix}$$

Langkah penyelesaian:
1. Baris 1, Kolom 1: Jumlahkan $2$ dan $5 \rightarrow 2 + 5 = 7$
2. Baris 1, Kolom 2: Jumlahkan $4$ dan $1 \rightarrow 4 + 1 = 5$
3. Baris 2, Kolom 1: Jumlahkan $1$ dan $7 \rightarrow 1 + 7 = 8$
4. Baris 2, Kolom 2: Jumlahkan $3$ dan $2 \rightarrow 3 + 2 = 5$

Maka hasil akhirnya adalah:

$$A + B = \begin{pmatrix} 2+5 & 4+1 \\ 1+7 & 3+2 \end{pmatrix} = \begin{pmatrix} 7 & 5 \\ 8 & 5 \end{pmatrix}$$

## Sifat-Sifat Penjumlahan Matriks

Penjumlahan matriks memiliki beberapa sifat penting yang mirip dengan penjumlahan bilangan biasa:
- Komutatif: $A + B = B + A$ (Urutan penjumlahan tidak mengubah hasil).
- Asosiatif: $(A + B) + C = A + (B + C)$ (Pengelompokan penjumlahan tidak mengubah hasil).
- Memiliki Unsur Identitas: $A + O = A$, di mana $O$ adalah matriks nol (matriks yang semua elemennya bernilai $0$).