# Invers Matriks

## Pengertian

Invers matriks bisa dianalogikan sebagai "kebalikan" dari suatu matriks. Jika pada bilangan biasa kebalikan dari $5$ adalah $\frac{1}{5}$ (atau $5^{-1}$) karena $5 \times \frac{1}{5} = 1$, maka di dalam matriks:Sebuah matriks $A$ jika dikalikan dengan inversnya (dilambangkan dengan $A^{-1}$) akan menghasilkan Matriks Identitas ($I$).

$$A \times A^{-1} = I$$

(Catatan: Matriks identitas $I$ adalah matriks khusus yang elemen diagonal utamanya bernilai $1$ dan elemen lainnya $0$, seperti $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$. Matriks ini bertindak seperti angka $1$ pada perkalian biasa).

## Syarat Matriks Punya Invers

Tidak semua matriks bisa memiliki invers. Ada dua syarat mutlak yang harus dipenuhi:

1. Harus Matriks Persegi: Jumlah baris dan kolomnya harus sama (misalnya $2 \times 2$, $3 \times 3$, dst).
2. Nilai Determinan Tidak Boleh Nol ($\text{det}(A) \neq 0$): Jika determinan suatu matriks bernilai $0$, matriks tersebut dinamakan Matriks Singular dan dipastikan tidak memiliki invers.

## 1. Invers Matriks Ukuran $2 \times 2$

Ini adalah bentuk yang paling dasar dan paling sering digunakan.Jika kita memiliki matriks $A$:

$$A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$$

Rumus untuk mencari inversnya adalah:

$$A^{-1} = \frac{1}{\text{det}(A)} \times \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$$

Dengan nilai determinan: $\text{det}(A) = (a \times d) - (b \times c)$

Langkah mudah menghafalnya:
1. Hitung determinannya: $(a \times d) - (b \times c)$.
2. Tukar posisi elemen diagonal utama ($a$ dan $d$ saling bertukar tempat).
3. Ubah tanda (kali dengan $-1$) elemen diagonal sekunder ($b$ dan $c$).

### Contoh Soal Matriks $2 \times 2$:

Diketahui matriks $A = \begin{pmatrix} 4 & 2 \\ 5 & 3 \end{pmatrix}$, cari $A^{-1}$!

- Langkah 1: Hitung Determinan

$$\text{det}(A) = (4 \times 3) - (2 \times 5) = 12 - 10 = 2$$

- Langkah 2: Masukkan ke Rumus

$$A^{-1} = \frac{1}{2} \times \begin{pmatrix} 3 & -2 \\ -5 & 4 \end{pmatrix}$$

- Langkah 3: Kalikan semua elemen dengan $\frac{1}{2}$

$$A^{-1} = \begin{pmatrix} \frac{3}{2} & \frac{-2}{2} \\ \frac{-5}{2} & \frac{4}{2} \end{pmatrix} = \begin{pmatrix} 1.5 & -1 \\ -2.5 & 2 \end{pmatrix}$$

## 2. Invers Matriks Ukuran $3 \times 3$

Untuk ukuran $3 \times 3$, langkahnya sedikit lebih panjang karena kita harus mencari matriks Kofaktor dan Adjoin terlebih dahulu.Rumus umumnya secara struktural tetap sama:

$$A^{-1} = \frac{1}{\text{det}(A)} \times \text{Adj}(A)$$

Tahapan mencarinya:
1. Cari Determinan: Biasanya menggunakan metode Sarrus (menambahkan dua kolom pertama di sebelah kanan matriks lalu menghitung jumlah perkalian diagonalnya).
2. Cari Matriks Minor & Kofaktor: Menghitung determinan sub-matriks kecil $2 \times 2$ dengan cara menutup baris dan kolom tertentu satu per satu, lalu memberikan tanda selang-seling $(+, -, +, \dots)$.
3. Cari Adjoin ($\text{Adj}$): Adjoin didapat dengan cara men-transpose matriks kofaktor (mengubah baris menjadi kolom).
4. Kalikan dengan $\frac{1}{\text{det}(A)}$.

## Sifat-Sifat Penting Invers Matriks

Berikut adalah beberapa sifat operasi invers yang sering keluar dalam ujian atau penyederhanaan rumus:

- $(A^{-1})^{-1} = A$ (Invers yang diinverskan lagi akan kembali ke matriks semula).
- $(A \times B)^{-1} = B^{-1} \times A^{-1}$ (Hati-hati: urutannya berbalik jika tanda kurung dibuka).
- $(A^T)^{-1} = (A^{-1})^T$ (Operasi transpose dan invers posisinya boleh ditukar).