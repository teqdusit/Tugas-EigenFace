# Persamaan Linear

## Pengertian

Persamaan Linear adalah sebuah persamaan matematika yang jika digambarkan ke dalam grafik, akan membentuk garis lurus.Kata kuncinya adalah "linear", yang berarti pangkat tertinggi dari variabel (seperti $x$ atau $y$) di dalam persamaan tersebut selalu satu. Jadi, tidak ada variabel yang dikuadratkan ($x^2$), diakar ($\sqrt{x}$), atau saling dikalikan ($xy$).

## 1. Bentuk Umum Persamaan Linear

Tergantung pada jumlah variabelnya, persamaan linear biasanya ditulis seperti ini:

### Satu Variabel
Hanya ada satu huruf yang tidak diketahui nilainya.

$$ax + b = 0$$

- Contoh: $2x - 6 = 0$
- Jika kita cari nilai $x$, maka $2x = 6$, sehingga $x = 3$.

### Dua Variabel
Memiliki dua huruf variabel (biasanya $x$ dan $y$). Bentuk ini sangat sering digunakan untuk membuat grafik fungsi di koordinat Kartesius.

$$y = mx + c$$

- $m$ adalah gradien atau kemiringan garis.
- $c$ adalah titik potong pada sumbu $y$ (di mana garis menabrak garis vertikal $y$).
- Contoh: $y = 2x + 1$

## Sistem Persamaan Linear (SPL)

Sering kali kita tidak hanya menghadapi satu persamaan, melainkan beberapa persamaan sekaligus yang saling berhubungan. Ini disebut Sistem Persamaan Linear.
Tujuan utama dari SPL adalah mencari satu nilai untuk variabel-variabelnya yang bisa memuaskan semua persamaan yang ada.

- Sistem Persamaan Linear Dua Variabel (SPLDV):

$$2x + y = 5$$

$$x - y = 1$$

Untuk menyelesaikan ini, kita mencari nilai $x$ dan $y$ yang cocok untuk kedua persamaan di atas (dalam contoh ini, $x = 2$ dan $y = 1$).

- Sistem Persamaan Linear Tiga Variabel (SPLTV):
Memiliki tiga variabel (misal $x$, $y$, dan $z$). Di dunia komputer dan aljabar linear, sistem ini bisa berkembang menjadi puluhan, ratusan, bahkan jutaan variabel.

## 3. Cara Menyelesaikan Sistem Persamaan Linear

Untuk mencari nilai variabel yang belum diketahui, ada beberapa metode dasar yang biasa digunakan:

1. Metode Substitusi: Mengubah satu persamaan menjadi bentuk tunggal (misal $x = ...$), lalu memasukkannya ke persamaan lain.
2. Metode Eliminasi: Menghilangkan salah satu variabel dengan cara menjumlahkan atau mengurangkan kedua persamaan.
3. Metode Grafik: Menggambar kedua garis persamaan pada grafik, lalu melihat di titik mana kedua garis tersebut saling berpotongan. Titik potong itulah jawabannya.
4. Metode Matriks (Aljabar Linear Komputasi): Untuk persamaan yang sangat banyak, komputer akan menyusun angka-angkanya menjadi sebuah matriks (kotak angka) lalu menyelesaikannya menggunakan algoritma seperti Eliminasi Gauss.

## 4. Mengapa Persamaan Linear Penting?
Meskipun terlihat sederhana, persamaan linear adalah fondasi dari banyak teknologi dan hitungan di dunia nyata:
- Prediksi Bisnis: Menghitung keuntungan berdasarkan jumlah barang yang terjual jika harga per barangnya konstan.
- Ilmu Komputer & AI: Algoritma kecerdasan buatan (Machine Learning) seperti Linear Regression menggunakan prinsip persamaan linear untuk memprediksi tren data (misalnya memprediksi harga rumah berdasarkan luas tanah).
- Fisika dan Teknik: Menghitung kecepatan konstan, arus listrik dalam rangkaian, atau distribusi beban pada jembatan.