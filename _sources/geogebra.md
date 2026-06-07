# Membuat Persamaan Linear dengan GeoGebra

## 1. Konsep Dasar Persamaan Linear
Persamaan linear dua variabel umumnya ditulis dalam bentuk:
$$y = mx + c$$
Atau bentuk implisit:
$$ax + by = c$$

* **$m$** adalah **gradien** (kemiringan garis).
* **$c$** adalah **titik potong** garis dengan sumbu-Y (intercept-Y).

GeoGebra adalah alat yang sangat kuat untuk memvisualisasikan bagaimana perubahan nilai $m$ dan $c$ akan mempengaruhi arah dan posisi garis secara langsung (*real-time*).

---

## 2. Cara Membuat Persamaan Linear di GeoGebra

Ada tiga cara utama yang sering digunakan di GeoGebra untuk membuat garis linear:

### Cara 1: Menginput Persamaan Langsung (Aljabar)
Jika Anda sudah memiliki persamaannya, Anda tinggal mengetiknya di bilah masukan (*Input Bar*).
1. Buka GeoGebra (Graphing Calculator atau Classic).
2. Pada kolom **Input**, ketik persamaannya. Contoh: `y = 2x + 3` lalu tekan **Enter**.
3. GeoGebra akan langsung menggambar garis tersebut di bidang Kartesius dan memberi nama garis tersebut (misalnya garis $f$).

### Cara 2: Menggunakan Dua Titik (Geometri)
Jika Anda hanya mengetahui dua titik yang dilewati garis:
1. Pilih alat **Point** (Titik) pada toolbar, lalu klik di dua tempat berbeda pada grafik untuk membuat titik $A$ dan $B$.
   * *Alternatif:* Ketik langsung di kolom input: `A = (1, 2)` dan `B = (3, 4)`.
2. Pilih alat **Line** pada toolbar, lalu klik titik $A$ kemudian klik titik $B$.
3. GeoGebra akan otomatis memunculkan persamaan linear dari garis tersebut di panel Aljabar sebelah kiri.

### Cara 3: Menggunakan Slider (Eksperimen Interaktif)
Ini adalah cara terbaik untuk memahami perilaku grafik secara dinamis:
1. Ketik `m = 1` di kolom Input (Ini akan membuat slider untuk gradien).
2. Ketik `c = 2` di kolom Input (Ini akan membuat slider untuk titik potong Y).
3. Ketik persamaan umum: `y = m*x + c` lalu tekan **Enter**.
4. Geser tombol slider $m$ dan $c$ yang muncul di layar. Perhatikan bagaimana grafik bergerak:
   * Jika $m$ diperbesar, garis menjadi lebih tegak.
   * Jika $m$ negatif, garis miring ke kiri bawah.
   * Jika $c$ diubah, garis akan bergeser naik atau turun.

---

## 3. Fitur Tambahan yang Berguna

Setelah garis terbentuk, Anda bisa menggunakan perintah-perintah berikut di kolom Input untuk menganalisis grafik:

* **Mencari Titik Potong Sumbu (Intercepts):**
  Ketik `Intersect(f, SumbuY)` atau cukup gunakan alat *Intersect* pada toolbar lalu klik garis dan sumbu X/Y untuk melihat titik potongnya secara presisi.
* **Menampilkan Nilai Kemiringan (Gradien):**
  Ketik `Slope(f)` atau pilih alat *Slope* dari toolbar lalu klik pada garis. GeoGebra akan menampilkan segitiga kemiringan beserta nilai $m$-nya pada grafik.

---

## 4. Latihan Praktis (Mandiri)

Cobalah langkah-langkah berikut di GeoGebra untuk menguji pemahaman Anda:

1. Buatlah grafik dari sistem persamaan linear dua variabel (SPLDV) berikut:
   * Garis 1: $x + y = 5$
   * Garis 2: $2x - y = 1$
2. Gunakan perintah atau alat `Intersect` untuk mengklik titik pertemuan kedua garis tersebut.
3. Catat koordinat titik potongnya! Koordinat $(x, y)$ tersebut merupakan **Himpunan Penyelesaian (HP)** dari sistem persamaan tersebut.