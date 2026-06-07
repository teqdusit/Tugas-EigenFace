# Tugas Evaluasi Determinan dan Invers Matriks

Materi ini disusun untuk memenuhi tugas evaluasi perhitungan determinan menggunakan metode ekspansi baris (Laplace) serta menghitung invers matriks menggunakan metode matriks adjoin.

---

## 1. Tinjauan Teoretis

### A. Determinan dengan Ekspansi Baris (Laplace)
Determinan dari matriks persegi $A$ berukuran $n \times n$ dapat dihitung dengan memilih salah satu baris secara bebas (misalkan baris ke-$i$) menggunakan rumus:

$\det(A) = \sum_{k=1}^{n} (-1)^{i+k} a_{ik} M_{ik}$

Dimana:
* $a_{ik}$ adalah elemen matriks $A$ pada baris ke-$i$ dan kolom ke-$k$.
* $M_{ik}$ adalah *minor* dari elemen $a_{ik}$, yaitu determinan submatriks yang diperoleh dengan menghapus baris ke-$i$ dan kolom ke-$k$.
* Kofaktor dari elemen $a_{ik}$ didefinisikan sebagai $C_{ik} = (-1)^{i+k} M_{ik}$.

> *Tips Praktis:* Pilih baris yang memiliki elemen angka $0$ atau $1$ paling banyak untuk meminimalkan dan mempercepat proses komputasi manual.

### B. Invers Matriks dengan Matriks Adjoin
Matriks persegi $A$ memiliki invers (bersifat invertible atau non-singular) jika dan hanya jika $\det(A) \neq 0$. Rumus umum invers matriks adalah:

$A^{-1} = \frac{1}{\det(A)} \operatorname{adj}(A)$

Dimana $\operatorname{adj}(A)$ adalah *matriks adjoin*, yaitu transpose dari matriks kofaktor $C$:

$\operatorname{adj}(A) = C^T = \begin{bmatrix} C_{11} & C_{21} & \dots & C_{n1} \\ C_{12} & C_{22} & \dots & C_{n2} \\ \dots & \dots & \dots & \dots \\ C_{1n} & C_{2n} & \dots & C_{nn} \end{bmatrix}$

---

## 2. Soal dan Pembahasan Lengkap

### BAGIAN A: Menghitung Determinan dengan Ekspansi Baris

#### *Soal 1 (Matriks $2 \times 2$)*
Hitunglah determinan matriks berikut menggunakan rumus ekspansi baris:
$$A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$$

*Pembahasan:*
Kita pilih ekspansi *Baris 1* ($i = 1$). Elemen-elemennya adalah $a_{11} = -7$ dan $a_{12} = -5$.
* *Minor $M_{11}$:* Hapus baris 1 kolom 1 $\rightarrow M_{11} = \det([4]) = 4$
* *Minor $M_{12}$:* Hapus baris 1 kolom 2 $\rightarrow M_{12} = \det([1]) = 1$

Masukkan ke dalam rumus ekspansi baris:
$\det(A) = (-1)^{1+1} a_{11} M_{11} + (-1)^{1+2} a_{12} M_{12}$
$\det(A) = (+1)(-7)(4) + (-1)(-5)(1)$
$\det(A) = -28 + 5$
$\det(A) = -23$

Jadi, determinan matriks $A$ adalah *$-23$*.

---

#### *Soal 2 (Matriks $3 \times 3$)*
Hitunglah determinan matriks berikut menggunakan rumus ekspansi baris:
$A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$

*Pembahasan:*
Perhatikan bahwa *Baris 3* memiliki elemen nol terbanyak: $\begin{bmatrix} 0 & 0 & 1 \end{bmatrix}$. Kita lakukan ekspansi pada *Baris 3* ($i = 3$) untuk mempercepat perhitungan.
* Elemen $a_{31} = 0 \rightarrow$ Suku bernilai $0$
* Elemen $a_{32} = 0 \rightarrow$ Suku bernilai $0$
* Elemen $a_{33} = 1$

Kita hanya perlu menghitung minor untuk $a_{33}$ (hapus baris 3 kolom 3):
$M_{33} = \det \begin{bmatrix} 0 & 2 \\ 1 & -2 \end{bmatrix} = (0 \cdot -2) - (2 \cdot 1) = 0 - 2 = -2$

Masukkan ke rumus ekspansi:
$\det(A) = (-1)^{3+3} a_{33} M_{33}$
$\det(A) = (+1)(1)(-2)$
$\det(A) = -2$

Jadi, determinan matriks $A$ adalah *$-2$*.

---

#### *Soal 3 (Matriks $4 \times 4$)*
Hitunglah determinan matriks berikut menggunakan rumus ekspansi baris:
$A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}$

*Pembahasan:*
Kita pilih ekspansi *Baris 1* ($i = 1$). Rumus ekspansinya adalah:
$\det(A) = a_{11}C_{11} + a_{12}C_{12} + a_{13}C_{13} + a_{14}C_{14}$
$\det(A) = (1)M_{11} - (-3)M_{12} + (1)M_{13} - (1)M_{14}$
$\det(A) = M_{11} + 3M_{12} + M_{13} - M_{14}$

Mari kita hitung sub-determinan matriks $3 \times 3$ (Minor):

1.  *Menghitung $M_{11}$* (Hapus baris 1, kolom 1):
    $M_{11} = \det \begin{bmatrix} 1 & 1 & 1 \\ 1 & -3 & 1 \\ 1 & 1 & -3 \end{bmatrix}$
     Ekspansi baris 1:
    $$M_{12} = -3 \cdot [9 - 1] - 1 \cdot [-3 - 1] + 1 \cdot [1 + 3]$$
    $$M_{12} = -3[8] - 1[-4] + 1[4] = -24 + 4 + 4 = -16$$

3.  *Menghitung $M_{13}$* (Hapus baris 1, kolom 3):
    $$M_{13} = \det \begin{bmatrix} -3 & 1 & 1 \\ 1 & 1 & 1 \\ 1 & 1 & -3 \end{bmatrix}$$
    Ekspansi baris 1:
    $$M_{13} = -3 \cdot [(-3) - 1] - 1 \cdot [(-3) - 1] + 1 \cdot [1 - 1]$$
    $$M_{13} = -3[-4] - 1[-4] + 0 = 12 + 4 = 16$$

4.  *Menghitung $M_{14}$* (Hapus baris 1, kolom 4):
    $$M_{14} = \det \begin{bmatrix} -3 & 1 & 1 \\ 1 & -3 & 1 \\ 1 & 1 & 1 \end{bmatrix}$$
    Ekspansi baris 1:
    $$M_{14} = -3 \cdot [-3 - 1] - 1 \cdot [1 - 1] + 1 \cdot [1 - (-3)]$$
    $$M_{14} = -3[-4] - 0 + 1[4] = 12 + 4 = 16$$

Gabungkan semua nilai minor ke dalam rumus determinan awal:
$$\det(A) = M_{11} + 3M_{12} + M_{13} - M_{14}$$
$$\det(A) = 16 + 3(-16) + 16 - 16$$
$$\det(A) = 16 - 48 + 16 - 16$$
$$\det(A) = -48$$

Jadi, determinan matriks $4 \times 4$ tersebut adalah *$-48$*.

---

### BAGIAN B: Menghitung Invers Matriks dengan Adjoin

#### *Soal 4 (Matriks $2 \times 2$)*
Gunakan rumus matriks adjoin untuk menghitung invers dari matriks berikut:
$$A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$$

*Pembahasan:*
Dari hasil pengerjaan Soal 1, kita tahu nilai $\det(A) = -23$.
Untuk matriks berukuran $2 \times 2$, nilai adjoin didapatkan langsung dengan menukar elemen diagonal utama dan mengubah tanda elemen diagonal sekunder:
$$\operatorname{adj}(A) = \begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix}$$

Maka invers matriks $A$ adalah:
$$A^{-1} = \frac{1}{\det(A)} \operatorname{adj}(A)$$
$$A^{-1} = \frac{1}{-23} \begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix} = \begin{bmatrix} -\frac{4}{23} & -\frac{5}{23} \\ \frac{1}{23} & \frac{7}{23} \end{bmatrix}$$

---

#### *Soal 5 (Matriks $3 \times 3$)*
Gunakan rumus matriks adjoin untuk menghitung invers dari matriks berikut:
$$A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$$

*Pembahasan:*
Dari hasil pengerjaan Soal 2, kita tahu nilai $\det(A) = -2$. Sekarang, kita cari 9 elemen matriks kofaktor $C_{ij} = (-1)^{i+j}M_{ij}$:

* $C_{11} = +\det \begin{bmatrix} -2 & -1 \\ 0 & 1 \end{bmatrix} = -2$
* $C_{12} = -\det \begin{bmatrix} 1 & -1 \\ 0 & 1 \end{bmatrix} = -(1) = -1$
* $C_{13} = +\det \begin{bmatrix} 1 & -2 \\ 0 & 0 \end{bmatrix} = 0$
* $C_{21} = -\det \begin{bmatrix} 2 & -3 \\ 0 & 1 \end{bmatrix} = -(2) = -2$
* $C_{22} = +\det \begin{bmatrix} 0 & -3 \\ 0 & 1 \end{bmatrix} = 0$
* $C_{23} = -\det \begin{bmatrix} 0 & 2 \\ 0 & 0 \end{bmatrix} = 0$
* $C_{31} = +\det \begin{bmatrix} 2 & -3 \\ -2 & -1 \end{bmatrix} = (-2) - (6) = -8$
* $C_{32} = -\det \begin{bmatrix} 0 & -3 \\ 1 & -1 \end{bmatrix} = -(0 - (-3)) = -3$
* $C_{33} = +\det \begin{bmatrix} 0 & 2 \\ 1 & -2 \end{bmatrix} = 0 - 2 = -2$

Susun matriks kofaktor $C$:
$$C = \begin{bmatrix} -2 & -1 & 0 \\ -2 & 0 & 0 \\ -8 & -3 & -2 \end{bmatrix}$$

Dapatkan nilai adjoin dengan melakukan transpose matriks kofaktor ($\operatorname{adj}(A) = C^T$):
$$\operatorname{adj}(A) = \begin{bmatrix} -2 & -2 & -8 \\ -1 & 0 & -3 \\ 0 & 0 & -2 \end{bmatrix}$$

Hitung nilai invers matriks:
$$A^{-1} = \frac{1}{-2} \begin{bmatrix} -2 & -2 & -8 \\ -1 & 0 & -3 \\ 0 & 0 & -2 \end{bmatrix} = \begin{bmatrix} 1 & 1 & 4 \\ \frac{1}{2} & 0 & \frac{3}{2} \\ 0 & 0 & 1 \end{bmatrix}$$

---

#### *Soal 6 (Matriks $4 \times 4$)*
Gunakan rumus matriks adjoin untuk menghitung invers dari matriks berikut:
$$A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}$$

*Pembahasan:*
Dari pengerjaan Soal 3, didapatkan nilai $\det(A) = -48$. Karena elemen-elemen matriks ini memiliki tingkat simetrisitas yang tinggi, kita dapat memanfaatkan sifat tersebut:

1.  *Elemen Diagonal Utama Kofaktor ($C_{11}, C_{22}, C_{33}, C_{44}$):*
    Nilai minor diagonal utamanya akan selalu bernilai sama dengan perhitungan $M_{11}$ pada langkah sebelumnya.
    $$C_{11} = C_{22} = C_{33} = C_{44} = 16$$

2.  *Elemen Non-Diagonal Kofaktor:*
    Sebagai contoh, kita ambil nilai $C_{12} = -M_{12} = -(-16) = 16$. Dikarenakan konfigurasi angka di luar diagonal utama bernilai konstan ($1$), maka seluruh kofaktor luar diagonal utama juga bernilai sama.
    $$C_{ij} = 16 \quad \text{untuk } i \neq j$$

Maka bentuk matriks kofaktor $C$ adalah matriks seragam berorde $4 \times 4$:
$$C = \begin{bmatrix} 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \end{bmatrix}$$

Karena seluruh elemennya bernilai seragam, maka $\operatorname{adj}(A) = C^T = C$.

Hitung nilai invers matriks:
$$A^{-1} = \frac{1}{-48} \begin{bmatrix} 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \\ 16 & 16 & 16 & 16 \end{bmatrix}$$

Sederhanakan pecahan dengan membagi tiap elemen dengan $-48$ (dimana $\frac{16}{-48} = -\frac{1}{3}$):
$$A^{-1} = \begin{bmatrix} -\frac{1}{3} & -\frac{1}{3} & -\frac{1}{3} & -\frac{1}{3} \\ -\frac{1}{3} & -\frac{1}{3} & -\frac{1}{3} & -\frac{1}{3} \\ -\frac{1}{3} & -\frac{1}{3} & -\frac{1}{3} & -\frac{1}{3} \\ -\frac{1}{3} & -\frac{1}{3} & -\frac{1}{3} & -\frac{1}{3} \end{bmatrix}$$