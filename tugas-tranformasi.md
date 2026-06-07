# Transformasi Linear Refleksi pada Vektor di Bidang Dua Dimensi

## Pengertian

Transformasi matriks adalah salah satu fondasi terpenting dalam matematika komputasi, grafika komputer, dan pengolahan citra (*image processing*). Melalui pendekatan linear algebra ini, kita dapat mengubah posisi, arah, ukuran, bahkan bentuk suatu objek dalam ruang dua dimensi ($2D$) maupun tiga dimensi ($3D$) secara efisien menggunakan operasi perkalian matriks.

Secara umum, transformasi linear dari titik awal $P(x, y)$ menuju titik bayangan $P'(x', y')$ dapat dinyatakan sebagai sistem persamaan linear:
$x' = ax + by$
$y' = cx + dy$

Dalam bentuk matriks, persamaan di atas diekspresikan secara ringkas sebagai:
$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$

Di mana matriks $M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$ disebut sebagai **Matriks Transformasi**.

---

## 1. Translasi (Pergeseran)

Translasi adalah transformasi yang memindahkan setiap titik pada bidang dengan jarak dan arah yang tetap. Berbeda dengan jenis transformasi lainnya, translasi murni dalam koordinat Kartesius standar $2D$ merupakan operasi **penjumlahan**, bukan perkalian matriks linear.

Jika suatu titik $P(x, y)$ digeser sejauh $a$ satuan searah sumbu $X$ dan $b$ satuan searah sumbu $Y$, maka komponen pergeserannya ditulis sebagai vektor $T = \begin{pmatrix} a \\ b \end{pmatrix}$.

### Persamaan Matriks Translasi
$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} x \\ y \end{pmatrix} + \begin{pmatrix} a \\ b \end{pmatrix}$

> **Catatan Teknis (Koordinat Homogen):**
> Dalam industri grafika komputer (seperti OpenGL atau game engine), agar translasi dapat dihitung menggunakan perkalian matriks yang seragam dengan transformasi lainnya, digunakan sistem **Koordinat Homogen** (*Homogeneous Coordinates*) berukuran $3 \times 3$:
> $$\begin{pmatrix} x' \\ y' \\ 1 \end{pmatrix} = \begin{pmatrix} 1 & 0 & a \\ 0 & 1 & b \\ 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \\ 1 \end{pmatrix}$$

---

## 2. Refleksi (Pencerminan)

Refleksi adalah transformasi geometri yang memetakan suatu titik atau objek dengan cara mencerminkannya terhadap sebuah garis pemandu atau titik pusat tertentu. Sifat utama refleksi adalah jarak objek asli ke cermin selalu sama dengan jarak cermin ke objek bayangan.

Berikut adalah representasi matriks untuk berbagai jenis refleksi standar $2D$:

### A. Refleksi Terhadap Sumbu-X
Mengubah tanda koordinat $y$ menjadi negatif, sedangkan koordinat $x$ tetap.
$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$

### B. Refleksi Terhadap Sumbu-Y
Mengubah tanda koordinat $x$ menjadi negatif, sedangkan koordinat $y$ tetap.
$\begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$

### C. Refleksi Terhadap Garis $y = x$
Menukar posisi koordinat $x$ menjadi $y$ dan sebaliknya.
$\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$

### D. Refleksi Terhadap Garis $y = -x$
Menukar posisi koordinat sekaligus mengubah kedua tandanya menjadi negatif.
$\begin{pmatrix} 0 & -1 \\ -1 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$

### E. Refleksi Terhadap Titik Pusat $O(0,0)$
Mengubah tanda kedua koordinat (ekuivalen dengan rotasi $180^\circ$).
$\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$

---

## 3. Rotasi (Perputaran)

Rotasi adalah transformasi yang memutar sebuah titik atau objek sejauh sudut $\theta$ terhadap suatu titik acuan tertentu. Secara konvensi matematika, arah putaran bernilai **positif ($+$) jika berlawanan arah jarum jam**, dan bernilai **negatif ($-$) jika searah jarum jam**.

### A. Rotasi dengan Pusat Titik Asal $O(0,0)$
Matriks rotasi diturunkan menggunakan koordinat polar dan prinsip trigonometri:
$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$

### B. Rotasi dengan Pusat Sembarang Titik $P(a,b)$
Untuk memutar objek terhadap titik yang bukan titik asal, kita perlu menggeser titik pusat tersebut ke $(0,0)$ terlebih dahulu, melakukan rotasi, lalu menggesernya kembali ke posisi semula:
$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix} \begin{pmatrix} x - a \\ y - b \end{pmatrix} + \begin{pmatrix} a \\ b \end{pmatrix}$

---

## 4. Dilatasi (Perkalian Skala)

Dilatasi adalah transformasi yang mengubah ukuran (memperbesar atau memperkecil) suatu objek tanpa mengubah bentuk aslinya. Perubahan ukuran ini ditentukan oleh **faktor skala $k$**.
- Jika $|k| > 1$, objek akan diperbesar.
- Jika $0 < |k| < 1$, objek akan diperkecil.
- Jika $k < 0$, bayangan objek akan terbalik dan terletak di sisi berlawanan dari pusat dilatasi.

### A. Dilatasi dengan Pusat $O(0,0)$
$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} k & 0 \\ 0 & k \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$

### B. Dilatasi dengan Pusat Sembarang Titik $P(a,b)$
$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} k & 0 \\ 0 & k \end{pmatrix} \begin{pmatrix} x - a \\ y - b \end{pmatrix} + \begin{pmatrix} a \\ b \end{pmatrix}$

---

## 5. Komposisi Transformasi Matriks

Komposisi transformasi terjadi ketika sebuah titik atau objek ditransformasikan secara berurutan oleh beberapa matriks transformasi (misalnya direfleksikan, kemudian dirotasikan, dan terakhir didilatasi).

Keunggulan utama menggunakan pendekatan matriks adalah kita dapat menggabungkan rentetan transformasi tersebut menjadi **satu buah matriks tunggal ($M_{\text{total}}$)** melalui perkalian matriks.

### Aturan Urutan Perkalian (Penting!)
Jika sebuah objek ditransformasikan berturut-turut oleh matriks $M_1$, kemudian dilanjutkan oleh $M_2$, dan dilanjutkan oleh $M_3$, maka urutan pengerjaan operasinya dituliskan dari **kanan ke kiri**:

$M_{\text{total}} = M_3 \times M_2 \times M_1$

Persamaan akhir untuk mencari bayangan koordinatnya adalah:
$\begin{pmatrix} x' \\ y' \end{pmatrix} = (M_3 \times M_2 \times M_1) \begin{pmatrix} x \\ y \end{pmatrix}$

> **Peringatan:** Perkalian matriks tidak bersifat komutatif ($M_1 \times M_2 \neq M_2 \times M_1$). Mengubah urutan perkalian matriks akan menghasilkan bayangan transformasi yang salah.

---

### D. Objek Transformasi: Persegi Panjang

Pada implementasi ini, objek yang ditransformasi adalah **persegi panjang**
yang didefinisikan oleh 4 titik sudut:

| Label | Posisi | Koordinat |
|-------|--------|-----------|
| $A$ | Kiri atas | $(x, y+h)$ |
| $B$ | Kanan atas | $(x+w, y+h)$ |
| $C$ | Kiri bawah | $(x, y)$ |
| $D$ | Kanan bawah | $(x+w, y)$ |

di mana $x, y$ adalah posisi sudut kiri bawah, $w$ adalah lebar, dan $h$ adalah tinggi.

Setiap sudut direfleksikan secara individual menggunakan rumus matriks refleksi,
menghasilkan titik $A', B', C', D'$ yang membentuk persegi panjang hasil refleksi.

---

## 6. Source Code Python

```python
import numpy as np
import matplotlib.pyplot as plt
import matplotlib.patches as patches
from matplotlib.widgets import Slider

fig, ax = plt.subplots(figsize=(11, 7))
plt.subplots_adjust(left=0.1, right=0.95, top=0.88, bottom=0.25)

mirror_angle = 90

def reflect_point(x, y, angle_deg):
    t = angle_deg * np.pi / 180
    rx = x * np.cos(2*t) + y * np.sin(2*t)
    ry = x * np.sin(2*t) - y * np.cos(2*t)
    return rx, ry

def draw(bx, by, rw, rh, angle):
    ax.clear()

    corners = {
        'A': (bx,      by + rh),
        'B': (bx + rw, by + rh),
        'C': (bx,      by),
        'D': (bx + rw, by)
    }

    ref_corners = {}
    for lbl, (cx, cy) in corners.items():
        rx, ry = reflect_point(cx, cy, angle)
        ref_corners[lbl+"'"] = (rx, ry)

    # Grid & axes
    ax.set_xlim(-8, 8)
    ax.set_ylim(-6, 6)
    ax.axhline(0, color='black', linewidth=0.8, alpha=0.4)
    ax.axvline(0, color='black', linewidth=0.8, alpha=0.4)
    ax.grid(True, alpha=0.25, linestyle='--')
    ax.set_xlabel('x', fontsize=12)
    ax.set_ylabel('y', fontsize=12)
    ax.set_title(f'Refleksi Persegi Panjang — θ = {int(angle)}°', fontsize=13)

    # Garis cermin
    t = angle * np.pi / 180
    L = 7
    ax.plot([-L*np.cos(t), L*np.cos(t)],
            [-L*np.sin(t), L*np.sin(t)],
            color='gray', linewidth=1.5,
            linestyle='--', label=f'Cermin θ={int(angle)}°', zorder=2)

    # Persegi panjang biru (Objek Asli)
    ax.add_patch(patches.Rectangle(
        (bx, by), rw, rh,
        linewidth=2, edgecolor='#3B82F6',
        facecolor='#3B82F6', alpha=0.15, zorder=3
    ))
    for lbl, (cx, cy) in corners.items():
        ax.plot(cx, cy, 'o', color='#3B82F6', markersize=8, zorder=5)
        ax.annotate(lbl, (cx, cy), xytext=(6,6),
                    textcoords='offset points',
                    fontsize=11, color='#3B82F6', fontweight='bold')

    # Persegi panjang merah (Hasil Refleksi)
    rx_all = [p[0] for p in ref_corners.values()]
    ry_all = [p[1] for p in ref_corners.values()]
    ax.add_patch(patches.Rectangle(
        (min(rx_all), min(ry_all)),
        abs(max(rx_all)-min(rx_all)),
        abs(max(ry_all)-min(ry_all)),
        linewidth=2, edgecolor='#EF4444',
        facecolor='#EF4444', alpha=0.15, zorder=3
    ))
    for lbl, (cx, cy) in ref_corners.items():
        ax.plot(cx, cy, 'o', color='#EF4444', markersize=8, zorder=5)
        ax.annotate(lbl, (cx, cy), xytext=(6,6),
                    textcoords='offset points',
                    fontsize=11, color='#EF4444', fontweight='bold')

    # Garis putus-putus antar sudut penghubung
    for lbl in ['A','B','C','D']:
        ox, oy = corners[lbl]
        rx2, ry2 = ref_corners[lbl+"'"]
        ax.plot([ox, rx2], [oy, ry2],
                color='gray', linewidth=0.8,
                linestyle=':', alpha=0.5, zorder=2)

    ax.legend(loc='upper right', fontsize=10)
    fig.canvas.draw_idle()

# ---- KONFIGURASI SLIDER ----
ax_x     = plt.axes([0.15, 0.17, 0.7, 0.03])
ax_y     = plt.axes([0.15, 0.12, 0.7, 0.03])
ax_ang   = plt.axes([0.15, 0.07, 0.7, 0.03])
ax_rw    = plt.axes([0.15, 0.02, 0.3, 0.03])
ax_rh    = plt.axes([0.55, 0.02, 0.3, 0.03])

sl_x   = Slider(ax_x,   'Geser X',   -6, 6,   valinit=-3, valstep=0.1)
sl_y   = Slider(ax_y,   'Geser Y',   -4, 4,   valinit= 1, valstep=0.1)
sl_ang = Slider(ax_ang, 'Sudut θ',    0, 180, valinit=90, valstep=1)
sl_rw  = Slider(ax_rw,  'Lebar',      0.5, 5, valinit= 2, valstep=0.5)
sl_rh  = Slider(ax_rh,  'Tinggi',     0.5, 4, valinit= 2, valstep=0.5)

def update(val):
    draw(sl_x.val, sl_y.val, sl_rw.val, sl_rh.val, sl_ang.val)

sl_x.on_changed(update)
sl_y.on_changed(update)
sl_ang.on_changed(update)
sl_rw.on_changed(update)
sl_rh.on_changed(update)

# Menampilkan grafik awal
draw(-3, 1, 2, 2, 90)
plt.show()

```

## 7. Hasil Visualisasi

Visualisasi menampilkan:

- **Persegi panjang biru** — objek asli yang dapat digeser bebas menggunakan slider
- **Persegi panjang merah** — hasil refleksi yang bergerak mengikuti secara otomatis
- **Garis cermin** — garis referensi abu-abu putus-putus yang dapat diputar
- **Garis penghubung** — menghubungkan tiap titik sudut asli ke titik refleksinya,
  membuktikan bahwa jarak tiap titik ke garis cermin adalah sama di kedua sisi

Ketika slider **Geser X** digeser ke kiri, persegi panjang merah bergerak ke kanan —
persis seperti bayangan di cermin. Ketika slider **Geser Y** digeser ke atas,
keduanya ikut naik bersama-sama karena refleksi mempertahankan komponen
yang sejajar dengan garis cermin.

---

## 8. Analisis Sifat Transformasi

Dari hasil visualisasi dapat diverifikasi bahwa refleksi memiliki sifat-sifat berikut:

**1. Isometri** — jarak antar titik dipertahankan:

$|AB| = |A'B'|, \quad |BC| = |B'C'|$

**2. Involusi** — refleksi dua kali menghasilkan identitas:

$R_\theta \cdot R_\theta = I$

artinya merefleksikan objek dua kali mengembalikan ke posisi semula.

**3. Determinan bernilai $-1$** — menunjukkan perubahan orientasi:

$\det(R_\theta) = \cos^2 2\theta + \sin^2 2\theta \cdot (-1) \cdot (-1) = -1$

**4. Matriks ortogonal** — invers sama dengan transpos:

$R_\theta^{-1} = R_\theta^T$

---

## 9. Kesimpulan

Dari implementasi dan visualisasi transformasi linear refleksi pada persegi panjang
di bidang dua dimensi, dapat disimpulkan:

1. **Refleksi adalah transformasi linear** karena dapat direpresentasikan sebagai
   perkalian matriks $R_\theta$ yang memenuhi syarat aditivitas dan homogenitas.

2. **Refleksi mempertahankan bentuk dan ukuran** — persegi panjang tetap
   berbentuk persegi panjang dengan luas dan panjang sisi yang identik setelah
   direfleksikan.

3. **Refleksi membalik orientasi** — susunan titik $A \to B \to C \to D$
   yang semula searah jarum jam menjadi berlawanan arah jarum jam pada
   hasil refleksi $A' \to B' \to C' \to D'$.

4. **Sudut cermin $\theta$ menentukan arah refleksi** — perubahan $\theta$
   mengubah posisi relatif objek refleksi terhadap objek asli, dengan
   kasus-kasus khusus pada $0°$, $45°$, $90°$, dan $135°$.

5. **Setiap titik memiliki jarak yang sama ke garis cermin** — titik asal
   dan titik refleksinya selalu berjarak sama terhadap garis cermin,
   yang terlihat dari garis penghubung putus-putus yang selalu tegak lurus
   terhadap garis cermin.