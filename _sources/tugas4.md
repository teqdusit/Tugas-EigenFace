# Tugas 4

## Operasi Baris Elementer (OBE)

Eliminasi Gauss adalah metode untuk menyelesaikan Sistem Persamaan Linear (SPL) dengan mengubah matriks augmentasi (gabungan koefisien dan konstanta) menjadi **Matriks Eselon Baris**. Target utama kita adalah membentuk *leading 1* (utama 1) secara diagonal dan membuat elemen di bawahnya menjadi 0.

---

## 1. Tiga Operasi Baris Elementer (OBE)
Untuk mengubah baris matriks, kita hanya diperbolehkan menggunakan 3 operasi berikut:
1. **Menukarkan** posisi dua baris ($R_i \leftrightarrow R_j$).
2. **Mengalikan** suatu baris dengan konstanta non-nol ($k \cdot R_i$).
3. **Menambahkan** kelipatan suatu baris ke baris lainnya ($R_i + k \cdot R_j$).

---

## 2. Struktur Matriks 4 Variabel & 4 Persamaan
Sistem persamaan dengan variabel $x, y, z, w$ akan diubah menjadi bentuk matriks augmentasi:

$$
\left[
\begin{array}{cccc|c}
a_1 & b_1 & c_1 & d_1 & e_1 \\
a_2 & b_2 & c_2 & d_2 & e_2 \\
a_3 & b_3 & c_3 & d_3 & e_3 \\
a_4 & b_4 & c_4 & d_4 & e_4 \\
\end{array}
\right]
$$

**Target Akhir (Matriks Eselon Baris):**
$$
\left[
\begin{array}{cccc|c}
1 & * & * & * & * \\
0 & 1 & * & * & * \\
0 & 0 & 1 & * & * \\
0 & 0 & 0 & 1 & * \\
\end{array}
\right]
$$
*(Tanda $*$ artinya bisa bernilai angka berapapun)*

---

## 3. Langkah-Langkah Sistematis (Strategi OBE)
Agar tidak membingungkan, lakukan eliminasi secara berurutan per kolom:

* **Langkah 1 (Kolom 1):** Buat elemen pojok kiri atas menjadi `1`. Lalu gunakan baris 1 untuk mengubah elemen di bawahnya (Baris 2, 3, dan 4) menjadi `0`.
* **Langkah 2 (Kolom 2):** Buat elemen diagonal pada baris 2 menjadi `1`. Lalu gunakan baris 2 untuk mengubah elemen di bawahnya (Baris 3 dan 4) menjadi `0`.
* **Langkah 3 (Kolom 3):** Buat elemen diagonal pada baris 3 menjadi `1`. Lalu gunakan baris 3 untuk mengubah elemen di bawahnya (Baris 4) menjadi `0`.
* **Langkah 4 (Kolom 4):** Buat elemen diagonal pada baris 4 menjadi `1`.
* **Langkah 5 (Substitusi Balik):** Cari nilai $w$ dari baris 4, lalu masukkan ke baris 3 untuk mendapat $z$, masukkan ke baris 2 untuk mendapat $y$, dan terakhir baris 1 untuk mendapat $x$.

---

## 4. Contoh Soal & Pembahasan

Selesaikan SPL berikut:
1. $x + y + z + w = 10$
2. $2x + y - z + w = 5$
3. $x - y + 2z - 2w = -2$
4. $-x + 2y - z + w = 4$

### Penyelesaian:

**Bentuk Matriks Awal:**
$$
\left[
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 10 \\
2 & 1 & -1 & 1 & 5 \\
1 & -1 & 2 & -2 & -2 \\
-1 & 2 & -1 & 1 & 4 \\
\end{array}
\right]
$$

#### Kolom 1 (Membuat Nol di bawah Utama 1)
Baris 1 sudah diawali angka `1`. Kita nolkan Baris 2, 3, dan 4:
* $R_2 - 2R_1 \rightarrow R_2$
* $R_3 - R_1 \rightarrow R_3$
* $R_4 + R_1 \rightarrow R_4$

Hasilnya:
$$
\left[
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 10 \\
0 & -1 & -3 & -1 & -15 \\
0 & -2 & 1 & -3 & -12 \\
0 & 3 & 0 & 2 & 14 \\
\end{array}
\right]
$$

#### Kolom 2 (Membuat Utama 1 di Baris 2 dan Nol di bawahnya)
Kalikan Baris 2 dengan $-1$ agar menjadi `1`:
* $-1 \cdot R_2 \rightarrow R_2$

$$
\left[
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 10 \\
0 & 1 & 3 & 1 & 15 \\
0 & -2 & 1 & -3 & -12 \\
0 & 3 & 0 & 2 & 14 \\
\end{array}
\right]
$$

Nolkan elemen di bawah diagonal baris 2:
* $R_3 + 2R_2 \rightarrow R_3$
* $R_4 - 3R_2 \rightarrow R_4$

Hasilnya:
$$
\left[
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 10 \\
0 & 1 & 3 & 1 & 15 \\
0 & 0 & 7 & -1 & 18 \\
0 & 0 & -9 & -1 & -31 \\
\end{array}
\right]
$$

#### Kolom 3 & 4 (Menyelesaikan Sisa Matriks)
Supaya perhitungan lebih mudah dan menghindari pecahan terlalu awal, kita bisa lakukan operasi antar baris terlebih dahulu. 
Tambahkan Baris 4 dengan Baris 3 ($R_4 + R_3 \rightarrow R_4$):
$$
\left[
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 10 \\
0 & 1 & 3 & 1 & 15 \\
0 & 0 & 7 & -1 & 18 \\
0 & 0 & -2 & -2 & -13 \\
\end{array}
\right]
$$

Bagi Baris 4 dengan $-2$ ($-\frac{1}{2} \cdot R_4 \rightarrow R_4$):
$$
\left[
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 10 \\
0 & 1 & 3 & 1 & 15 \\
0 & 0 & 7 & -1 & 18 \\
0 & 0 & 1 & 1 & 6.5 \\
\end{array}
\right]
$$

Tukarkan Baris 3 dan Baris 4 ($R_3 \leftrightarrow R_4$) agar angka `1` naik ke atas:
$$
\left[
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 10 \\
0 & 1 & 3 & 1 & 15 \\
0 & 0 & 1 & 1 & 6.5 \\
0 & 0 & 7 & -1 & 18 \\
\end{array}
\right]
$$

Nolkan angka 7 di Baris 4 menggunakan Baris 3 ($R_4 - 7R_3 \rightarrow R_4$):
$$
\left[
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 10 \\
0 & 1 & 3 & 1 & 15 \\
0 & 0 & 1 & 1 & 6.5 \\
0 & 0 & 0 & -8 & -27.5 \\
\end{array}
\right]
$$

Bagi Baris 4 dengan $-8$ ($-\frac{1}{8} \cdot R_4 \rightarrow R_4$):
$$
\left[
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 10 \\
0 & 1 & 3 & 1 & 15 \\
0 & 0 & 1 & 1 & 6.5 \\
0 & 0 & 0 & 1 & 3.4375 \\
\end{array}
\right]
$$

#### Substitusi Balik
Dari matriks terakhir, kita dapatkan sistem persamaan baru:
1. $w = 3.4375$
2. $z + w = 6.5 \rightarrow z = 6.5 - 3.4375 = 3.0625$
3. $y + 3z + w = 15 \rightarrow y = 15 - 3(3.0625) - 3.4375 = 2.375$
4. $x + y + z + w = 10 \rightarrow x = 10 - 2.375 - 3.0625 - 3.4375 = 1.125$

**Solusi:** $x = 1.125$, $y = 2.375$, $z = 3.0625$, $w = 3.4375$.

---

## 5. Soal Latihan Mandiri

Selesaikan sistem persamaan linear berikut menggunakan metode Eliminasi Gauss (OBE):

### Soal 1 (Tingkat Dasar - Hasil Bulat)
$$
\begin{aligned}
x + y + z + w &= 6 \\
2x + 3y - z + w &= 5 \\
-x + 2y + 3z - w &= 7 \\
3x + y - 2z + 2w &= 1
\end{aligned}
$$
*(Petunjuk Kunci Jawaban: $x=1, y=2, z=2, w=1$)*

### Soal 2 (Tingkat Menengah)
$$
\begin{aligned}
2x + y + 2z - w &= 5 \\
x + 2y - z + 2w &= 4 \\
3x - y + z + w &= 6 \\
x + y + z + w &= 4
\end{aligned}
$$

### Tips Sukses Mengerjakan OBE:
* Fokus selesaikan kolom demi kolom dari kiri ke kekanan.
* Jangan terburu-buru membagi baris dengan angka besar jika masih bisa dikurangi/ditambah dengan baris lain agar tidak pusing dengan angka pecahan di awal langkah.
* Teliti tanda positif `+` dan negatif `-` saat melakukan operasi perkalian dan penjumlahan baris.