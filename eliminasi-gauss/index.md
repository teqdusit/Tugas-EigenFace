# Eliminasi Gauss

## Pengertian

Eliminasi Gauss adalah salah satu metode paling populer dan mendasar dalam aljabar linear untuk menyelesaikan Sistem Persamaan Linear (SPL).
Metode ini dinamai dari matematikawan terkenal, Carl Friedrich Gauss. Prinsip utamanya adalah mengubah sistem persamaan linear yang rumit menjadi bentuk yang lebih sederhana (disebut Bentuk Eselon Baris), sehingga nilai variabel-variabelnya bisa ditemukan dengan mudah melalui hitung mundur (substitusi balik).
Dalam dunia komputer, metode inilah yang menjadi dasar bagi software untuk menyelesaikan ribuan persamaan linear sekaligus.

## 1. Ide Dasar: Mengubah Persamaan Menjadi Matriks

Misalkan kita punya sistem persamaan linear seperti ini: 

$2x + y - z = 8$

$-3x - y + 2z = -11$

$-2x + y + 2z = -3$

Untuk menyelesaikannya dengan Eliminasi Gauss, kita membuang huruf variabelnya ($x, y, z$) sementara waktu dan mengambil angka-angkanya saja untuk dimasukkan ke dalam kotak yang disebut Matriks Augmentasi (Augmented Matrix):

$$\left[
\begin{array}{ccc|c}
2 & 1 & -1 & 8 \\
-3 & -1 & 2 & -11 \\
-2 & 1 & 2 & -3 \\
\end{array}
\right]$$

## 2. Target Eliminasi Gauss: Matriks Segitiga Atas

Tujuan dari Eliminasi Gauss adalah melakukan serangkaian operasi matematika pada baris-baris matriks tersebut agar elemen-elemen di bawah diagonal utama berubah menjadi nol.
Jika area di bawah diagonal utama sudah menjadi nol semua, matriks ini disebut berbentuk Segitiga Atas (Bentuk Eselon Baris).

## 3. Langkah-Langkah Operasi Baris Elemeneter (OBE)

Untuk mengubah angka di bawah diagonal menjadi nol, kita menggunakan Operasi Baris Elementer (OBE). Ada tiga aturan legal yang boleh kita lakukan pada baris matriks:
1. Menukar posisi dua baris.

2. Mengalikan atau membagi sebuah baris dengan angka bukan nol.

3. Menambahkan atau mengurangkan kelipatan suatu baris ke baris yang lain.

Prosesnya secara urut:
- Langkah 1: Buat angka pertama di baris pertama kolom pertama menjadi angka $1$ (disebut Pivot atau satu utama).
- Langkah 2: Gunakan baris pertama tersebut untuk mengubah angka-angka di bawahnya (pada kolom pertama) menjadi $0$ lewat operasi pengurangan/penjumlahan baris.
- Langkah 3: Pindah ke baris kedua kolom kedua, jadikan angka di sana sebagai Pivot berikutnya, lalu jadikan angka di bawahnya menjadi $0$.
- Langkah 4: Lakukan terus secara diagonal ke bawah sampai terbentuk matriks segitiga atas.

## 4. Tahap Akhir: Substitusi Balik (Back Substitution)
Setelah bagian bawah diagonal menjadi nol, kita kembalikan lagi bentuk matriks tadi menjadi persamaan matematika biasa.
Sebagai gambaran hasil akhir, baris paling bawah matriks akan menyisakan satu variabel saja, misalnya:

$$0x + 0y + 1z = 2 \quad \Rightarrow \quad z = 2$$

Karena nilai $z$ sudah ketahuan, kita naik ke baris di atasnya untuk mencari nilai $y$:

$y + (\text{angka} \times z) = \text{hasil}$

Masukkan nilai $z = 2$ ke persamaan tersebut, maka nilai $y$ akan didapat.Terakhir, naik lagi ke baris paling atas, masukkan nilai $y$ dan $z$ yang sudah ketemu untuk mendapatkan nilai $x$. Selesai!

## 5. Kelebihan Eliminasi Gauss

- Sangat Terstruktur: Langkah-langkahnya pasti dan mekanis, sehingga sangat mudah diubah menjadi kode program komputer (algoritma).

- Efisien untuk Komputer: Dibandingkan rumus manual seperti aturan Cramer (yang pakai determinan), Eliminasi Gauss jauh lebih cepat diselesaikan oleh prosesor komputer ketika jumlah persamaannya mencapai ratusan atau ribuan.