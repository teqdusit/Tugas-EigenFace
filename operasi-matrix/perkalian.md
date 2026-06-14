# Perkalian Matrix

## Pengertian 

Perkalian matriks adalah salah satu operasi yang paling sering digunakan, namun aturan mainnya cukup berbeda dengan perkalian bilangan biasa. Di sini, kita tidak mengalikan elemen yang posisinya sama, melainkan menggunakan prinsip Baris dikali Kolom.

Berikut adalah penjelasan lengkap mengenai syarat, rumus, dan langkah-langkah menghitungnya.

## Syarat Utama Perkalian Matriks

Dua matriks baru bisa dikalikan jika jumlah kolom matriks pertama sama dengan jumlah baris matriks kedua.
Jika matriks pertama ($A$) berukuran $m \times n$ dan matriks kedua ($B$) berukuran $n \times p$, maka keduanya bisa dikalikan karena angka tengahnya sama ($n$). Hasil kalinya nanti akan menjadi matriks baru ($C$) dengan ukuran mengambil angka luar, yaitu $m \times p$.
Penting: Jika syarat ini tidak terpenuhi, maka kedua matriks tidak dapat dikalikan.

## Cara Menghitung (Konsep Baris $\times$ Kolom)

Cara menghitungnya adalah dengan mengambil sebaris elemen dari matriks pertama, lalu kalikan satu per satu dengan elemen di satu kolom matriks kedua, kemudian jumlahkan hasilnya.Misalkan kita mengalikan dua matriks berukuran $2 \times 2$:

$$A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}, \quad B = \begin{pmatrix} e & f \\ g & h \end{pmatrix}$$

Rumus hasil perkaliannya adalah:

$$A \times B = \begin{pmatrix} (a \times e) + (b \times g) & (a \times f) + (b \times h) \\ (c \times e) + (d \times g) & (c \times f) + (d \times h) \end{pmatrix}$$

Contoh Soal Langkah demi Langkah
Diketahui dua matriks berikut:

$$A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}, \quad B = \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix}$$

Mari kita hitung elemen untuk matriks hasil satu per satu:
1. Baris 1 (Matriks A) $\times$ Kolom 1 (Matriks B) $\rightarrow$ untuk posisi kiri atas:

$$(1 \times 5) + (2 \times 7) = 5 + 14 = 19$$

2. Baris 1 (Matriks A) $\times$ Kolom 2 (Matriks B) $\rightarrow$ untuk posisi kanan atas:

$$(1 \times 6) + (2 \times 8) = 6 + 16 = 22$$

3. Baris 2 (Matriks A) $\times$ Kolom 1 (Matriks B) $\rightarrow$ untuk posisi kiri bawah:

$$(3 \times 5) + (4 \times 7) = 15 + 28 = 43$$

4. Baris 2 (Matriks A) $\times$ Kolom 2 (Matriks B) $\rightarrow$ untuk posisi kanan bawah:

$$(3 \times 6) + (4 \times 8) = 18 + 32 = 50$$

Gabungkan semua hasil di atas ke dalam matriks baru:

$$A \times B = \begin{pmatrix} 19 & 22 \\ 43 & 50 \end{pmatrix}$$

## Sifat Unik Perkalian Matriks

Ada beberapa sifat penting yang perlu diingat agar tidak keliru saat mengerjakan soal:
- Tidak Komutatif: Berbeda dengan perkalian angka biasa ($2 \times 3 = 3 \times 2$), pada matriks secara umum posisi tidak boleh dibalik:

$$A \times B \neq B \times A$$

- Asosiatif: Jika ada tiga matriks yang dikalikan, pengelompokannya bebas selama urutannya tetap:

$$(A \times B) \times C = A \times (B \times C)$$

- Matriks Identitas ($I$): Ada matriks khusus yang bertindak seperti angka $1$. Jika suatu matriks dikalikan dengan matriks identitas, hasilnya adalah matriks itu sendiri:

$$A \times I = I \times A = A$$

(Contoh matriks identitas $2 \times 2$ adalah $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$)

