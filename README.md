# Pencarian Rute Optimal Lampung-Medan dengan Algoritma A*

Sebuah implementasi dari algoritma pencarian A* (A-Star) untuk menemukan rute perjalanan darat yang optimal dari Bandar Lampung menuju Medan. Proyek ini menganalisis dua skenario optimisasi: mencari **rute tercepat** berdasarkan total waktu tempuh dan **rute termurah** berdasarkan total biaya tol.

## Latar Belakang

Dalam masalah pencarian rute, seringkali terdapat banyak kemungkinan jalur yang bisa ditempuh. Algoritma pencarian graf seperti A* sangat efektif untuk menyelesaikan masalah ini karena kemampuannya untuk secara cerdas menjelajahi kemungkinan-kemungkinan tersebut. A* tidak hanya mempertimbangkan biaya yang telah dikeluarkan (`g(n)`), tetapi juga menggunakan estimasi biaya ke tujuan (`h(n)`) untuk memandu pencarian ke arah yang paling menjanjikan, sehingga jauh lebih efisien daripada metode pencarian buta (*brute-force*).

## Fitur Utama

-   **Pencarian Multi-Kriteria**: Mampu mencari rute terbaik berdasarkan **waktu tempuh** atau **biaya tol**.
-   **Pemodelan Graf Dinamis**: Secara otomatis membaca data jaringan jalan dari file `.csv` dan mengubahnya menjadi struktur data graf (*adjacency list*) yang siap digunakan.
-   **Penerapan Heuristik**: Menggunakan fungsi heuristik yang informatif (estimasi waktu ke tujuan) untuk mempercepat proses pencarian rute tercepat.
-   **Output Komprehensif**: Menampilkan rute yang ditemukan secara jelas, lengkap dengan rincian total jarak, total estimasi waktu, dan total estimasi biaya.
-   **Kode Fleksibel**: Fungsi inti `a_star_search` didesain untuk dapat digunakan kembali dengan berbagai tipe biaya (`cost_type`) tanpa mengubah logika utamanya.

## Teknologi & Environment

| Teknologi | Versi | Deskripsi |
| :--- | :--- | :--- |
| Python | 3.13.3 | Bahasa pemrograman utama yang digunakan. |
| pandas | 2.3.0 | Library untuk membaca dan memanipulasi data dari file CSV. |
| heapq | Bawaan | Modul standar Python untuk implementasi *priority queue* yang efisien, komponen inti dari algoritma A*. |

## Struktur Proyek
/
├── searching.ipynb         # File utama Jupyter Notebook berisi kode, analisis, dan output.
└── lampungmedan.csv        # File dataset yang berisi data segmen rute, jarak, waktu, dan biaya.

## Panduan Penggunaan

### 1. Prasyarat

Pastikan Anda memiliki perangkat lunak berikut terinstal di sistem Anda:
-   Python 3
-   pip (Package Installer for Python)
-   Jupyter Notebook (opsional, jika ingin menjalankan file `.ipynb`)

### 2. Instalasi

a. **Clone Repositori** (jika proyek ada di Git) atau unduh semua file ke dalam satu folder.
   
b. **Instal Dependensi**
   Buka terminal atau command prompt, navigasikan ke folder proyek, dan jalankan perintah berikut untuk menginstal library yang diperlukan:
   ```bash
   pip install pandas
```
### 3. Menjalankan Program

- Melalui Jupyter Notebook dari terminal:
```bash
jupyter notebook
```
Lalu, buka file _searching.ipynb_ di browser.
- Melalui Python dari terminal:
```bash
searching.py
```

## Contoh Hasil Eksekusi
Output yang akan ditampilkan setelah program berhasil dieksekusi:
```
✅ Berhasil memuat data dari CSV dan membuat graph.

==================================================
Mencari rute optimal dari Lampung ke Medan...
==================================================

✅ Rute TERCEPAT (Berdasarkan Waktu Tempuh)
   Jalur             : Lampung -> Palembang -> Jambi -> Pekanbaru -> Rantau Prapat -> Medan
   Total Jarak       : 1690.00 km
   Total Waktu       : 25.70 jam
   Estimasi Biaya Tol: Rp 637.000

----------------------------------------

✅ Rute TERMURAH (Berdasarkan Biaya Tol)
   Jalur             : Lampung -> Baturaja -> Lubuk Linggau -> Bukittinggi -> Padang Sidempuan -> Medan
   Total Jarak       : 1435.00 km
   Total Waktu       : 28.70 jam
   Estimasi Biaya Tol: Rp 0
```
