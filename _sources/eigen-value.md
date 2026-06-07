# Eigen Value

Mari kita pelajari konsep dasar Eigenvalue dari sudut pandang aljabar linear analitik hingga implementasi komputasi numerik 

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


## 2. Contoh Implementasi dan hasil
1. Memahami konsep nilai eigen (*eigenvalue*) pada matriks simetris ukuran $2 \times 2$.
2. Mengimplementasikan **Algoritma Iterasi QR** sebanyak 10 iterasi untuk menunjukkan proses konvergensi.
3. Menghasilkan matriks segitiga atas di mana elemen diagonal utamanya adalah nilai eigen yang diharapkan, yaitu $\lambda_1 = 3$ dan $\lambda_2 = 1$.

---

## Teori Dasar & Soal

Diberikan sebuah matriks simetris $A_0$:
$$A_0 = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$$

### Algoritma Iterasi QR
Untuk setiap iterasi $k = 0, 1, 2, \dots, 9$:
1. Faktorkan matriks $A_k$ menjadi $Q_k$ (matriks ortogonal) dan $R_k$ (matriks segitiga atas), sehingga:
   $$A_k = Q_k R_k$$
2. Hitung matriks baru untuk iterasi berikutnya dengan mengalikan terbalik hasil dekomposisi tersebut:
   $$A_{k+1} = R_k Q_k$$
3. Ulangi proses ini sebanyak 10 kali. Seiring bertambahnya iterasi, elemen di bawah diagonal utama ($a_{21}$) akan mendekati $0$, dan nilai-nilai pada diagonal utama akan konvergen menuju nilai eigen dari matriks tersebut.

---

## Langkah Penyelesaian (Contoh: Iterasi 1)

Untuk melakukan dekomposisi $A_0 = Q_0 R_0$, kita dapat menggunakan teknik **Rotasi Givens** untuk mengeliminasi elemen $a_{21}$ (membuatnya menjadi 0).

### 1. Menghitung Nilai Cosine ($c$) dan Sine ($s$)
Dari matriks $A_0 = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$, diperoleh elemen $a_{11} = 2$ dan $a_{21} = 1$.
$$c = \frac{a_{11}}{\sqrt{a_{11}^2 + a_{21}^2}} = \frac{2}{\sqrt{2^2 + 1^2}} = \frac{2}{\sqrt{5}} \approx 0.8944$$
$$s = \frac{a_{21}}{\sqrt{a_{11}^2 + a_{21}^2}} = \frac{1}{\sqrt{2^2 + 1^2}} = \frac{1}{\sqrt{5}} \approx 0.4472$$

### 2. Membentuk Matriks Ortogonal $Q_0$ dan Segitiga Atas $R_0$
Matriks rotasi transpose $Q_0^T$ didefinisikan sebagai:
$$Q_0^T = \begin{pmatrix} c & s \\ -s & c \end{pmatrix} = \begin{pmatrix} 0.8944 & 0.4472 \\ -0.4472 & 0.8944 \end{pmatrix}$$

Maka, matriks $Q_0$ (transpose dari $Q_0^T$) adalah:
$$Q_0 = \begin{pmatrix} 0.8944 & -0.4472 \\ 0.4472 & 0.8944 \end{pmatrix}$$

Matriks $R_0$ diperoleh dari hasil kali $Q_0^T A_0$:
$$R_0 = \begin{pmatrix} 0.8944 & 0.4472 \\ -0.4472 & 0.8944 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix} = \begin{pmatrix} 2.2361 & 1.7889 \\ 0 & 1.3416 \end{pmatrix}$$

### 3. Menghitung Matriks Baru $A_1$
$$A_1 = R_0 Q_0 = \begin{pmatrix} 2.2361 & 1.7889 \\ 0 & 1.3416 \end{pmatrix} \begin{pmatrix} 0.8944 & -0.4472 \\ 0.4472 & 0.8944 \end{pmatrix} = \begin{pmatrix} 2.8000 & 0.6000 \\ 0.6000 & 1.2000 \end{pmatrix}$$

> **Analisis Awal:** Setelah iterasi pertama, nilai diagonal ($2.8$ dan $1.2$) sudah mulai bergerak mendekati target nilai eigen yaitu $3$ dan $1$. Sementara nilai *off-diagonal* menyusut dari $1.0$ menjadi $0.6$.

---

## Tabel Hasil Konvergensi Hingga 10 Iterasi

Proses di atas diulang kembali dengan cara yang sama untuk $A_1, A_2, \dots, A_9$ hingga menghasilkan $A_{10}$. Berikut adalah tabel perkembangan nilai elemen matriks pada setiap iterasi:

| Iterasi ($k$) | $a_{11}$ | $a_{12}$ | $a_{21}$ | $a_{22}$ |
| :---: | :---: | :---: | :---: | :---: |
| **0 (Awal)** | **2.0000** | 1.0000 | 1.0000 | **2.0000** |
| **1** | 2.8000 | 0.6000 | 0.6000 | 1.2000 |
| **2** | 2.9730 | 0.2297 | 0.2297 | 1.0270 |
| **3** | 2.9969 | 0.0789 | 0.0789 | 1.0031 |
| **4** | 2.9997 | 0.0264 | 0.0264 | 1.0003 |
| **5** | 3.0000 | 0.0088 | 0.0088 | 1.0000 |
| **6** | 3.0000 | 0.0029 | 0.0029 | 1.0000 |
| **7** | 3.0000 | 0.0010 | 0.0010 | 1.0000 |
| **8** | 3.0000 | 0.0003 | 0.0003 | 1.0000 |
| **9** | 3.0000 | 0.0001 | 0.0001 | 1.0000 |
| **10** | **3.0000** | 0.0000 | **0.0000** | **1.0000** |

---

## Kesimpulan Analisis

Berdasarkan hasil simulasi 10 iterasi menggunakan metode Iterasi QR, diperoleh matriks akhir:
$$A_{10} \approx \begin{pmatrix} 3.0000 & 0.0000 \\ 0.0000 & 1.0000 \end{pmatrix}$$

1. **Pembentukan Matriks Segitiga Atas:** Elemen di bawah diagonal utama ($a_{21}$) berhasil tereduksi secara signifikan hingga mencapai angka **$0.0000$** (konvergen). Hal ini membuktikan bahwa algoritma berhasil membentuk matriks segitiga atas (bahkan matriks diagonal sempurna karena sifat awal matriks yang simetris).
2. **Kesesuaian Nilai Eigen:** Elemen pada diagonal utama menunjukkan angka **3** dan **1**. Hal ini sesuai dengan nilai eigen teoritis yang diharapkan dari matriks $A_0$.
3. **Laju Konvergensi:** Algoritma ini menunjukkan konvergensi yang relatif cepat pada matriks ukuran $2 \times 2$, di mana pada iterasi ke-5 nilai eigen sudah sangat mendekati nilai presisi aslinya.