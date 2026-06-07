# SageMath

## 1. Apa itu SageMath?
**SageMath** (sebelumnya bernama SAGE - *System for Algebra and Geometry Experimentation*) adalah sistem komputer aljabar (Computer Algebra System / CAS) yang bersifat *open-source* (gratis dan bebas dikembangkan). 

SageMath menggabungkan kekuatan berbagai software matematika open-source yang sudah ada (seperti NumPy, SciPy, Matplotlib, Maxima, GAP, R, dan Singular) ke dalam satu antarmuka terpadu menggunakan bahasa pemrograman **Python**.

---

## 2. Mengapa Menggunakan SageMath?
* **Berbasis Python:** Tidak perlu mempelajari bahasa pemrograman baru yang rumit jika sudah memahami dasar-dasar Python.
* **Alternatif Software Komersial:** Menjadi kompetitor gratis dan terbuka untuk software matematika berbayar seperti *MATLAB, Mathematica, Maple,* dan *Magma*.
* **Sangat Lengkap:** Mendukung berbagai cabang matematika mulai dari aljabar dasar, kalkulus, teori bilangan, kriptografi, graf, hingga linear aljabar.

---

## 3. Fitur Utama SageMath
1. **Aljabar Linear & Matriks:** Mampu menyelesaikan operasi matriks, mencari determinan, invers, nilai eigen, hingga Operasi Baris Elementer (OBE).
2. **Kalkulus Simbolik:** Menyelesaikan turunan (derivatives), integral tentu/tak tentu, limit, dan deret Taylor secara simbolik (bukan hanya numerik).
3. **Visualisasi Data:** Membuat grafik 2D dan 3D dengan kualitas tinggi secara mudah.
4. **Teori Bilangan & Kriptografi:** Menyediakan fungsi tingkat lanjut untuk menguji bilangan prima, faktorisasi, dan simulasi algoritma keamanan.

---

## 4. Contoh Penggunaan Dasar (Sintaks SageMath)

Berikut adalah beberapa contoh kode sederhana bagaimana SageMath menyelesaikan persoalan matematika:

### a. Menghitung Turunan dan Integral (Kalkulus)
```python
# Mendefinisikan variabel x
x = var('x')

# Menghitung turunan dari f(x) = sin(x^2)
f = sin(x^2)
print("Turunan:", diff(f, x))

# Menghitung integral dari g(x) = 3x^2
g = 3*x^2
print("Integral:", integral(g, x))

