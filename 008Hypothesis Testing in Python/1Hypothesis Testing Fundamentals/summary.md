Secara singkat, file tersebut mempelajari tentang Pengujian Hipotesis (Hypothesis Testing). Ini adalah metode statistik fundamental untuk membuat keputusan berdasarkan data.

Tujuan utamanya adalah untuk menentukan apakah sebuah hasil atau perbedaan yang kita lihat dalam data (misalnya, kenaikan penjualan sebesar 43.4%) benar-benar nyata (disebut signifikan secara statistik) atau kemungkinan besar hanya terjadi karena kebetulan acak.

#############################################

Rangkuman Teknis

Proses yang dijelaskan dalam file tersebut pada dasarnya mengikuti langkah-langkah ini:


*Membuat Hipotesis: Kita mulai dengan dua pernyataan yang saling bersaing.

        - Hipotesis Nol (H0 ): Ini adalah asumsi awal, atau status quo. Biasanya menyatakan "tidak ada efek" atau "tidak ada perbedaan". Contoh: "Menampilkan iklan diskon tidak akan mengubah jumlah penjualan.".

        - Hipotesis Alternatif (HA): Ini adalah ide baru yang ingin kita buktikan. Contoh: "Menghapus iklan diskon justru akan meningkatkan penjualan.".

*Mengumpulkan Data Sampel: Kita tidak bisa menguji seluruh populasi (misalnya, semua gamer di dunia), jadi kita mengambil sampel data. Dalam contoh, ini adalah data penjualan dari grup kontrol (yang melihat iklan) dan grup perlakuan (yang tidak melihat iklan).


*Menghitung Statistik Uji (Z-score): Kita menghitung sebuah nilai yang disebut Z-score. Pikirkan Z-score sebagai "skor kejutan". Skor ini mengukur seberapa jauh hasil dari sampel kita (misalnya, rata-rata penjualan di grup perlakuan) dari apa yang kita harapkan jika Hipotesis Nol itu benar.

        - Z-score yang dekat dengan 0 berarti hasilnya tidak mengejutkan (sesuai harapan H0).

        - Z-score yang jauh dari 0 (positif atau negatif) berarti hasilnya mengejutkan (tidak sesuai harapan H0).

 - Menghitung P-value: Berdasarkan Z-score, kita menghitung p-value. P-value adalah probabilitas mendapatkan hasil yang sama ekstremnya (atau lebih ekstrem) dengan yang kita amati, 

dengan asumsi Hipotesis Nol itu benar.

        P-value besar: Berarti hasil yang kita lihat sangat mungkin terjadi karena kebetulan saja. Ini mendukung Hipotesis Nol (H0).

        P-value kecil: Berarti hasil yang kita lihat sangat tidak mungkin terjadi karena kebetulan. Ini memberikan bukti kuat untuk menolak Hipotesis Nol (H0) dan menerima Hipotesis Alternatif (HA).


- Membuat Keputusan: Kita membandingkan p-value dengan ambang batas yang kita tentukan sebelumnya, yang disebut Tingkat Signifikansi (α), biasanya 0.05 (atau 5%)

        Jika 
        p-value ≤α, kita "menolak Hipotesis Nol". Artinya, kita punya cukup bukti untuk mengatakan bahwa hasilnya signifikan secara statistik

        Jika 
        p-value > α, kita "gagal menolak Hipotesis Nol". Artinya, kita tidak punya cukup bukti untuk mengatakan hasilnya signifikan; bisa jadi hanya kebetulan.


Analogi sederhananya adalah seperti 

sidang pengadilan:

        Hipotesis Nol (H0): Terdakwa diasumsikan tidak bersalah.

        Hipotesis Alternatif (HA): Terdakwa bersalah.

        Data/Bukti: Fakta yang disajikan di pengadilan.

        P-value: Probabilitas melihat bukti tersebut jika terdakwa memang tidak bersalah.

        Keputusan: Jika buktinya sangat kuat (p-value sangat kecil), hakim akan menolak asumsi "tidak bersalah" dan menyatakan terdakwa bersalah.

#################################

Implementasi di Kehidupan Nyata

Metode ini sangat umum digunakan di berbagai bidang untuk membuat keputusan berbasis data.

#Marketing (A/B Testing) 🧪: Ini adalah contoh utama dalam file tersebut. Sebuah perusahaan e-commerce ingin tahu apakah mengubah warna tombol "Beli Sekarang" dari biru menjadi hijau akan meningkatkan penjualan.

H0: Warna tombol tidak berpengaruh pada penjualan.

HA: Tombol hijau akan meningkatkan penjualan.
Mereka akan membagi pengunjung website menjadi dua grup, mengukur hasilnya, dan melakukan pengujian hipotesis untuk memutuskan apakah perubahan warna tersebut layak diimplementasikan secara permanen.


#Kesehatan & Farmasi 💊: Sebelum sebuah obat baru disetujui, perusahaan farmasi harus membuktikan bahwa obat itu efektif.

H0: Obat baru tidak lebih baik dari plasebo (obat kosong).

HA: Obat baru lebih efektif daripada plasebo dalam menyembuhkan penyakit.
Pasien dibagi menjadi dua grup (satu mendapat obat, satu plasebo), dan hasilnya dianalisis secara statistik. Jika p-value sangat kecil, obat tersebut dianggap efektif.

#Manufaktur & Kontrol Kualitas 🏭: Sebuah pabrik mengubah salah satu mesinnya. Mereka ingin tahu apakah mesin baru ini menghasilkan lebih sedikit produk cacat.

H0: Tingkat produk cacat dari mesin baru sama dengan mesin lama.

HA: Tingkat produk cacat dari mesin baru lebih rendah.
Mereka mengambil sampel produk dari kedua mesin dan menggunakan pengujian hipotesis untuk menentukan apakah investasi pada mesin baru tersebut benar-benar mengurangi cacat produksi.

####################################

Apakah Ini Bisa Menjadi Template Default?

Jawaban singkatnya: Ya, kerangka berpikirnya adalah template default, tetapi implementasi teknisnya tidak selalu sama.

Sebagai Kerangka Berpikir (Mindset): YA! ✅
Proses logis dari:

    Mendefinisikan pertanyaan/masalah.

    Membuat asumsi awal (H0).

    Mengajukan ide baru (HA).

    Mengumpulkan data untuk mengujinya.

    Membuat keputusan berdasarkan bukti statistik.
    ... adalah fondasi dari pengambilan keputusan berbasis data (data-driven decision making). Pola pikir ini adalah template yang harus selalu digunakan dalam proyek analisis data, riset, dan pengembangan produk.


Sebagai Implementasi Teknis (Code): TIDAK SELALU! ❌
File tersebut secara spesifik menggunakan z-test dengan bantuan bootstrap untuk menghitung standar error. Ini adalah salah satu dari banyak jenis uji statistik. Pilihan uji yang tepat sangat bergantung pada:

    Jenis Data: Apakah Anda membandingkan rata-rata (seperti gaji), proporsi (seperti persentase orang), atau data kategori?
    Jumlah Sampel: Apakah sampel Anda besar atau kecil?
    Distribusi Data: Apakah data Anda terdistribusi normal?


Ada banyak metode lain seperti t-test, ANOVA, Chi-squared test, dll. Jadi, meskipun alur kerjanya mirip, kode dan rumus matematikanya bisa berbeda-beda untuk setiap kasus.

Singkatnya, metodologi pengujian hipotesis adalah template fundamental dalam dunia data, tetapi alat (uji statistik) yang Anda gunakan harus disesuaikan dengan pekerjaan yang sedang dihadapi.