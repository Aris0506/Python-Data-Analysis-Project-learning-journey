# Catatan Pembelajaran: Pengantar Statistik dengan Python

Ini adalah ringkasan poin-poin penting yang saya pelajari dari materi "Introduction to Statistics in Python", beserta latihan kuis dan mini-project.

## 1. Konsep Dasar Statistik

* **Statistik**: Ilmu pengumpulan dan analisis data.
* **Statistik Deskriptif**: Mendeskripsikan dan meringkas data yang ada (misal: rata-rata tinggi badan kelas).
* **Statistik Inferensial**: Menggunakan sampel data untuk membuat kesimpulan tentang populasi yang lebih besar (misal: menyimpulkan tinggi badan rata-rata siswa di seluruh sekolah dari sampel beberapa kelas).

## 2. Jenis-Jenis Data

Memahami jenis data sangat penting untuk memilih analisis statistik yang tepat.

* **Numerik (Kuantitatif)**: Data berbasis angka.
    * **Kontinu**: Dapat mengambil nilai apa pun dalam rentang tertentu (misal: tinggi badan, suhu, waktu). `(Diukur)`
    * **Diskrit**: Hanya dapat mengambil nilai tertentu, biasanya bilangan bulat (misal: jumlah anak, jumlah mobil). `(Dihitung)`
* **Kategoris (Kualitatif)**: Data yang mewakili karakteristik atau label.
    * **Nominal**: Kategori tanpa urutan yang melekat (misal: jenis kelamin, warna mata). `(Tidak Berurutan)`
    * **Ordinal**: Kategori dengan urutan atau peringkat yang jelas (misal: tingkat kepuasan: buruk, sedang, baik). `(Berurutan)`

## 3. Ukuran Pemusatan Data (Measures of Center)

Menggambarkan nilai "tipikal" atau pusat data.

* **Mean (Rata-rata)**: Jumlah semua nilai dibagi dengan banyaknya data.
    * **Penting**: Sangat sensitif terhadap nilai ekstrem (outlier).
* **Median (Nilai Tengah)**: Nilai tengah dari data yang telah diurutkan.
    * **Penting**: Lebih tahan (resisten) terhadap outlier dibandingkan mean.
* **Modus (Mode)**: Nilai yang paling sering muncul.

## 4. Ukuran Penyebaran Data (Measures of Spread)

Menggambarkan seberapa tersebar atau bervariasinya data.

* **Varian (Variance)**: Rata-rata dari kuadrat jarak setiap titik data dari mean.
* **Simpangan Baku (Standard Deviation)**: Akar kuadrat dari varian.
    * **Penting**: Memiliki unit yang sama dengan data asli, sehingga lebih mudah diinterpretasikan daripada varian.
* **Rentang Interkuartil (Interquartile Range - IQR)**: Selisih antara kuartil ketiga (Q3) dan kuartil pertama (Q1).
    * **Penting**: Mengukur penyebaran 50% data di bagian tengah dan tidak terpengaruh oleh outlier.
    * **Outlier**: Sebuah titik data dianggap outlier jika < $Q1 - 1.5 \times IQR$ atau > $Q3 + 1.5 \times IQR$.

## 5. Pelajaran Penting dari Praktik (Mini-Project)

### a. Pemilihan Statistik yang Tepat untuk Perbandingan

* Ketika membandingkan **"pola tipikal"** antar kelompok, **rata-rata (mean)** dan **median** adalah pilihan yang lebih tepat.
* **Jumlah total (`sum`)** dari suatu kolom numerik dapat menyesatkan untuk perbandingan antar kelompok jika ukuran (jumlah anggota) setiap kelompok tidak sama. Total yang lebih besar bisa jadi hanya karena kelompok tersebut memiliki lebih banyak anggota.

### b. Menghitung Frekuensi dan Ukuran Grup

* **Untuk menghitung frekuensi nilai unik dalam satu kolom (jumlah anggota per kategori):**
    * Gunakan `DataFrame['kolom'].value_counts()`. Ini adalah metode paling langsung dan efisien.
    * Atau, gunakan `DataFrame.groupby('kolom').size()`. Ini juga efisien dan berguna jika Anda memperluas analisis `groupby` lainnya.
    * `DataFrame.groupby('kolom').count()` juga bisa digunakan, terutama jika Anda ingin menghitung entri non-null di beberapa kolom per grup.

* **`groupby()` vs. `value_counts()`**:
    * `value_counts()` ideal untuk menghitung frekuensi satu kolom secara cepat.
    * `groupby()` lebih fleksibel dan kuat untuk melakukan berbagai agregasi (mean, median, sum, min, max, std, dll.) pada satu atau beberapa kolom, berdasarkan satu atau lebih kolom pengelompokan.

### c. Agregasi `sum()`

* `DataFrame.groupby('kolom_grup')['kolom_numerik'].sum()` digunakan untuk menjumlahkan semua nilai dalam `kolom_numerik` untuk setiap kategori di `kolom_grup`.
* Ini adalah metrik yang sah, misalnya untuk melihat "kontribusi total" suatu kelompok terhadap suatu variabel, tetapi interpretasinya harus hati-hati agar tidak disalahartikan sebagai "pola tipikal" atau "jumlah anggota".

---
