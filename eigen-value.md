# Ringkasan Materi & Tugas: Komputasi Eigenvalue (Teori & Metode QR)

Halaman ini berisi ringkasan konsep dasar Eigenvalue dari sudut pandang aljabar linear analitik hingga implementasi komputasi numerik menggunakan metode **QR Iteration**.

---

## 1. Konsep Dasar & Pengertian Analitik

Dalam aljabar linear, jika kita memiliki sebuah matriks persegi $A$ dan kita mengalikannya dengan sebuah vektor $x$, biasanya vektor tersebut akan berubah arah dan ukurannya. Namun, ada beberapa vektor spesial yang **tidak berubah arahnya** setelah dikalikan dengan matriks $A$. Vektor tersebut hanya menjadi lebih panjang, lebih pendek, atau berbalik arah ($180^\circ$).

* **Eigenvector (Vektor Eigen):** Vektor spesial $x$ (bukan vektor nol) yang arahnya tetap konisten setelah dilakukan transformasi matriks.
* **Eigenvalue (Nilai Eigen):** Faktor skala atau nilai $\lambda$ (lambda) yang menunjukkan seberapa besar vektor $x$ tersebut diperpanjang atau diperpendek.

### Persamaan Utama:
$$A \cdot x = \lambda \cdot x$$

Untuk mencari nilai $\lambda$ secara manual (analitik), kita mengubah persamaan di atas menjadi **Persamaan Karakteristik**:
$$\det(A - \lambda I) = 0$$

Dari persamaan determinan inilah kita mencari akar-akar polinomial untuk mendapatkan nilai $\lambda$.

---

## 2. Pendekatan Komputasi Numerik (Metode QR Iteration)

Mencari akar persamaan karakteristik secara manual sangat mudah untuk matriks ukuran $2 \times 2$. Namun, bagi komputer yang menangani data raksasa, menghitung determinan polinomial derajat tinggi sangatlah berat. Oleh karena itu, digunakan metode pendekatan iteratif seperti **Dekomposisi QR**.

### Alur Algoritma QR:
1. Matriks pada iterasi ke-$k$ ($A_k$) difaktorkan menjadi perkalian dua matriks:
   * $Q$ = Matriks Ortogonal ($Q^T \cdot Q = I$)
   * $R$ = Matriks Segitiga Atas (*Upper Triangular*)
2. Setelah didapat $A_k = Q_k \cdot R_k$, kita membentuk matriks baru untuk iterasi berikutnya dengan membalik urutan perkaliannya:
   $$A_{k+1} = R_k \cdot Q_k$$
3. Jika proses ini diulang terus-menerus secara iteratif, nilai di luar diagonal utama matriks $A$ lama-kelamaan akan mengecil menuju nol ($0$). 
4. Hasil akhir diagonal utama pada matriks $A$ baru tersebut merupakan **perkiraan nilai Eigenvalue**.

---

## 3. Data Hasil Simulasi Program (Tugas)

Berikut adalah simulasi jalannya program komputasi QR Iteration dengan input matriks awal:
$$A = \begin{pmatrix} 5 & 2 \\ 2 & 2 \end{pmatrix}$$

### === Iterasi 1 ===

**Matriks $Q$:**
```text
[[ 0.92847669 -0.37139068]
 [ 0.37139068  0.92847669]]