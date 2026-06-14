# Pembagian Matrix

## Pengertian

Secara teknis, dalam aljabar linear tidak ada operasi pembagian matriks seperti halnya pembagian angka biasa ($A \div B$ atau $\frac{A}{B}$ itu tidak terdefinisi).Namun, kita bisa melakukan operasi yang setara dengan pembagian dengan memanfaatkan konsep Matriks Invers.Ingat kembali prinsip matematika dasar: membagi dengan suatu angka sama saja dengan mengalikan dengan kebalikannya.
- Contoh: $6 \div 2$ sama dengan $6 \times \frac{1}{2}$ atau $6 \times 2^{-1}$.

Pada matriks, konsep kebalikan ini disebut Invers Matriks (dilambangkan dengan $B^{-1}$). Jadi, alih-alih membagi matriks $A$ dengan matriks $B$, kita mengalikan matriks $A$ dengan invers dari matriks $B$.

## Dua Kemungkinan Rumus "Pembagian" Matriks

Karena perkalian matriks tidak bersifat komutatif ($A \times B \neq B \times A$), urutan posisi peletakan matriks sangatlah penting. Jika kita memiliki persamaan matriks dan ingin mencari matriks $X$, ada dua kondisi:

### Kondisi 1: Matriks $B$ ada di depan
Jika persamaannya adalah:

$$B \times X = A$$

Untuk mencari $X$, kita kalikan invers $B$ di sisi kiri:

$$X = B^{-1} \times A$$

### Kondisi 2: Matriks $B$ ada di belakang
Jika persamaannya adalah:

$$X \times B = A$$

Untuk mencari $X$, kita kalikan invers $B$ di sisi kanan:

$$X = A \times B^{-1}$$

## Syarat Pembagian Matriks (Invers)

Tidak semua matriks bisa dijadikan "pembagi" (punya invers). Matriks $B$ harus memenuhi syarat berikut:
1. Harus Matriks Persegi: Jumlah baris dan kolomnya sama (misal $2 \times 2$, $3 \times 3$).
2. Nilai Determinan Tidak Boleh Nol ($\text{det}(B) \neq 0$): Matriks yang determinannya nol disebut matriks singular dan tidak memiliki invers (sama seperti angka 0 dalam bilangan biasa yang tidak bisa menjadi pembagi).

## Cara Mencari Invers Matriks (Ukuran $2 \times 2$)

Untuk matriks berukuran $2 \times 2$:

$$B = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$$

Rumus inversnya adalah:

$$B^{-1} = \frac{1}{\text{det}(B)} \times \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$$

Di mana nilai determinan $\text{det}(B) = (a \times d) - (b \times c)$

## Contoh Langkah demi Langkah

Misalkan kita ingin menyelesaikan "pembagian" untuk mencari matriks $X$ dari kondisi $B \times X = A$, dengan:

$$B = \begin{pmatrix} 4 & 2 \\ 5 & 3 \end{pmatrix}, \quad A = \begin{pmatrix} 10 & 8 \\ 13 & 11 \end{pmatrix}$$

### Langkah 1: Cari Invers Matriks $B$
- Hitung determinan $B$:

$$\text{det}(B) = (4 \times 3) - (2 \times 5) = 12 - 10 = 2$$

- Masukkan ke rumus invers (tukar posisi $a$ dan $d$, beri tanda negatif pada $b$ dan $c$):

$$B^{-1} = \frac{1}{2} \times \begin{pmatrix} 3 & -2 \\ -5 & 4 \end{pmatrix} = \begin{pmatrix} 1.5 & -1 \\ -2.5 & 2 \end{pmatrix}$$

### Langkah 2: Kalikan $B^{-1}$ dengan $A$

$$X = B^{-1} \times A$$

$$X = \begin{pmatrix} 1.5 & -1 \\ -2.5 & 2 \end{pmatrix} \times \begin{pmatrix} 10 & 8 \\ 13 & 11 \end{pmatrix}$$

Mari kita hitung dengan prinsip perkalian matriks (Baris $\times$ Kolom):
- Baris 1 $\times$ Kolom 1: $(1.5 \times 10) + (-1 \times 13) = 15 - 13 = 2$
- Baris 1 $\times$ Kolom 2: $(1.5 \times 8) + (-1 \times 11) = 12 - 11 = 1$
- Baris 2 $\times$ Kolom 1: $(-2.5 \times 10) + (2 \times 13) = -25 + 26 = 1$
- Baris 2 $\times$ Kolom 2: $(-2.5 \times 8) + (2 \times 11) = -20 + 22 = 2$
Maka hasil matriks $X$ adalah:

$$X = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$$