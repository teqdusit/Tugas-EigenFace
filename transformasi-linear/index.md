# Tranformasi Linear

## Pengertian

Transformasi Linear adalah sebuah fungsi atau pemetaan matematika yang memindahkan/mengubah suatu vektor dari satu ruang vektor (domain) ke ruang vektor lainnya (kodomain), dengan syarat perubahan tersebut harus menjaga sifat garis lurus dan kesebandingan.Secara visual, bayangkan kamu memiliki sebuah gambar atau grafik di atas kertas karet. Jika kamu menarik, merenggangkan, memutar, atau membalik kertas tersebut tanpa membuatnya melengkung, robek, atau bergeser dari titik pusat $(0,0)$, maka kamu baru saja melakukan Transformasi Linear.

## 1. Dua Syarat Mutlak Transformasi Linear

Sebuah fungsi $T$ (misalkan memetakan vektor $u$ dan $v$) disebut sebagai transformasi linear jika dan hanya jika memenuhi dua aturan berikut:

1. Aditif (Penjumlahan):

$$T(u + v) = T(u) + T(v)$$

Artinya, kamu boleh menjumlahkan dua vektor terlebih dahulu baru ditransformasikan, atau mentransformasikan masing-masing vektor baru dijumlahkan. Hasilnya harus sama.

2. Homogen (Perkalian Skalar):

$$T(c \cdot u) = c \cdot T(u)$$

Di mana $c$ adalah sebuah angka (skalar). Artinya, jika vektor input dikalikan 2, maka vektor hasil transformasinya juga harus menjadi 2 kali lebih panjang. Transformasi linear wajib memetakan vektor nol ke vektor nol ($T(0) = 0$). Jadi, titik pusat $(0,0)$ tidak boleh bergeser posisi.

## 2. Hubungan Erat dengan Matriks

Di dalam komputer, kita tidak menuliskan rumus fungsi yang panjang untuk melakukan transformasi linear. Kita menggunakan Matriks.Setiap transformasi linear dari ruang dimensi $n$ ke dimensi $m$ selalu bisa diwakili oleh sebuah perkalian matriks tunggal. Hubungannya ditulis seperti ini:

$$T(x) = A \cdot x$$

Di mana $A$ adalah Matriks Transformasi dan $x$ adalah vektor koordinat awal.

## 3. Jenis-Jenis Transformasi Linear (Beserta Contoh Matriksnya)

Berikut adalah beberapa operasi grafik 2D yang paling sering digunakan dalam pemrograman game atau grafika komputer:
### a. Rotasi (Perputaran)

Memutar vektor berlawanan arah jarum jam sebesar sudut $\theta$ dengan titik pusat $(0,0)$.
- Matriks Transformasi:

$$\begin{bmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{bmatrix}$$

### b. Scaling (Perubahan Skala/Ukuran)

Memperbesar atau memperkecil ukuran objek. Misalkan kita ingin memperbesar sumbu $x$ sebanyak $k_x$ kali dan sumbu $y$ sebanyak $k_y$ kali.
- Matriks Transformasi:

$$\begin{bmatrix} k_x & 0 \\ 0 & k_y \end{bmatrix}$$

### c. Refleksi (Pencerminan)

Mencerminkan objek terhadap suatu garis. Contohnya, mencerminkan objek terhadap sumbu $x$.
- Matriks Transformasi:

$$\begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}$$

### c. Shearing (Pergeseran Kemiringan)

Menggeser satu sumbu secara konstan sementara sumbu lainnya tetap, sehingga objek terlihat miring (seperti bentuk jajaran genjang).
- Matriks Transformasi (Shear horizontal):

$$\begin{bmatrix} 1 & k \\ 0 & 1 \end{bmatrix}$$

## 4. Kernel dan Range

Saat mempelajari transformasi linear, ada dua istilah ruang yang sangat penting untuk dipahami:
- Kernel (atau Null Space): Kumpulan semua vektor asal ($x$) yang setelah ditransformasikan oleh $T$, hasilnya amblas menjadi vektor nol ($0$).
- Range (atau Image): Kumpulan semua hasil vektor yang mungkin dicapai setelah vektor-vektor asal ditransformasikan oleh $T$.

## 5. Penerapan di Dunia Nyata

- Grafika Komputer & Game 3D: Ketika kamu menggerakkan kamera di dalam game (maju, mundur, menoleh), komputer sedang mengalikan semua koordinat objek 3D di dunia game tersebut dengan matriks transformasi linear agar posisinya berubah di layar monitor secara real-time.

- Pengolahan Citra (Image Processing): Fitur crop, resize, rotate, hingga efek filter miring pada aplikasi edit foto memanfaatkan perkalian matriks transformasi linear pada piksel gambar.

- Kecerdasan Buatan (Data Reduction): Teknik seperti PCA (Principal Component Analysis) menggunakan transformasi linear untuk memutar dan memproyeksikan data berdimensi tinggi (ribuan kolom) ke dimensi yang lebih kecil agar lebih mudah diproses oleh komputer tanpa kehilangan informasi penting.