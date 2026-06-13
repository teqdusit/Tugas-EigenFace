# Determinan

## pengertian

Determinan adalah sebuah nilai numerik (angka tunggal) yang hanya bisa dihitung dari sebuah matriks persegi (matriks yang jumlah baris dan kolomnya sama, seperti $2 \times 2$, $3 \times 3$, dst.).Jika matriks adalah sebuah kumpulan angka yang menyusun suatu transformasi ruang, maka determinan adalah satu angka yang menunjukkan bagaimana transformasi tersebut mengubah "skala" atau "ukuran" dari ruang tersebut.Notasi determinan untuk matriks $A$ biasanya ditulis sebagai $\text{det}(A)$ atau $|A|$.

## 1. Arti Geometris: Apa yang Diwakili oleh Determinan?

Sebelum masuk ke rumus, bayangkan determinan secara visual:
- Pada matriks $2 \times 2$, nilai determinan mewakili luas daerah (paralelogram) yang dibentuk oleh vektor-vektor kolom matriks tersebut.
- Pada matriks $3 \times 3$, nilai determinan mewakili volume ruang (paralelepipedum) yang dibentuk oleh vektor-vektornya.
- Jika $\text{det}(A) = 2$, artinya transformasi matriks tersebut membuat luas/volume objek menjadi 2 kali lipat lebih besar.
- Jika $\text{det}(A) = 0$, artinya ruang tersebut "tertekan" hingga gepeng (luas atau volumenya menjadi nol). Ini tanda bahwa matriks tersebut tidak memiliki kebalikan (invers).

## 2. Cara Menghitung Determinan

Cara menghitung determinan berbeda-beda tergantung pada ukuran matriksnya.

### Matriks $2 \times 2$
Ini adalah bentuk yang paling sederhana. Cukup kali silang diagonal utama lalu kurangi dengan perkalian diagonal sekunder.

Jika $A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}$, maka:

$$\text{det}(A) = (a \times d) - (b \times c)$$

- Contoh: $A = \begin{bmatrix} 3 & 2 \\ 1 & 4 \end{bmatrix}$

$$\text{det}(A) = (3 \times 4) - (2 \times 1) = 12 - 2 = 10$$

### Matriks $3 \times 3$ (Metode Sarrus)
Untuk matriks $3 \times 3$, metode yang paling sering digunakan secara manual adalah Metode Sarrus. Caranya adalah dengan menuliskan kembali dua kolom pertama di sebelah kanan matriks, lalu menjumlahkan hasil kali diagonal yang mengarah ke kanan bawah dan menguranginya dengan hasil kali diagonal yang mengarah ke kanan atas.

### Matriks Ukuran Besar ($4 \times 4$ ke atas)

Metode Sarrus tidak bisa digunakan untuk matriks berukuran $4 \times 4$ atau lebih besar. Untuk matriks besar, kita menggunakan metode:
1. Ekspansi Kofaktor (Laplace): Memecah matriks besar menjadi matriks-matriks kecil secara rekursif.
2. Eliminasi Gauss: Mengubah matriks menjadi matriks segitiga atas melalui OBE. Jika matriks sudah menjadi segitiga atas, nilai determinannya sangat mudah dicari, yaitu cukup mengalikan semua angka yang ada di diagonal utamanya. Metode inilah yang dipakai oleh komputer karena jauh lebih cepat.

## 3. Sifat-Sifat Penting Determinan

Memahami sifat determinan akan sangat membantu mempermudah perhitungan tanpa harus menghitung baris demi baris:
- Matriks Identitas: Determinan dari matriks identitas ($I$) selalu sama dengan $1$.
- Transpos Matriks: Nilai determinan dari matriks yang dibalik baris dan kolomnya tetap sama: $\text{det}(A^T) = \text{det}(A)$.
- Perkalian Matriks: $\text{det}(A \times B) = \text{det}(A) \times \text{det}(B)$.
- Baris/Kolom Nol: Jika ada satu baris atau satu kolom yang semua angkanya adalah $0$, maka determinannya otomatis $0$.
- Baris/Kolom Kembar: Jika ada dua baris atau dua kolom yang angkanya sama atau kelipatannya (saling bergantung linear), determinannya adalah $0$.

## 4. Mengapa Determinan Sangat Penting?

Dalam komputasi dan aljabar linear, determinan bertindak sebagai "alarm" atau indikator utama untuk mengetahui karakteristik suatu sistem:

- Menentukan Keberadaan Invers: Sebuah matriks punya invers (bisa dibagi) jika dan hanya jika $\text{det}(A) \neq 0$. Jika $\text{det}(A) = 0$, matriks itu disebut Matriks Singular (tidak punya invers).
- Menyelesaikan SPL: Digunakan dalam Aturan Cramer untuk mencari solusi persamaan linear.
- Mencari Eigenvalue: Dalam analisis matriks tingkat lanjut, determinan digunakan untuk menyelesaikan persamaan karakteristik $\text{det}(A - \lambda I) = 0$ guna menemukan eigenvalue yang penting untuk kestabilan sistem dan algoritma kecerdasan buatan.