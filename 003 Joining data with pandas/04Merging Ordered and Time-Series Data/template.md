Template Alur Kerja Penggabungan Time-Series
Langkah 1: Persiapan dan Pembersihan Data (Preprocessing) 🧹
- Konversi ke datetime
Pastikan kolom tanggal/waktu sudah dalam tipe datetime menggunakan pd.to_datetime().
Alasan: Pandas tidak bisa membandingkan waktu jika masih berbentuk string.

- Urutkan berdasarkan waktu
Gunakan .sort_values() untuk mengurutkan kedua DataFrame berdasarkan kolom waktu.
Catatan: Fungsi seperti merge_asof memerlukan data yang sudah terurut.

- Tangani data hilang (NaN)
Tentukan strategi pengisian nilai hilang sebelum penggabungan, misalnya menggunakan forward fill (.ffill()).



Langkah 2: Pilih Metode Penggabungan yang Tepat 🧠
- Cocokkan waktu persis sama?
Gunakan pd.merge() atau pd.merge_ordered() untuk data dengan stempel waktu identik.

- Cocokkan waktu paling mendekati (asynchronous)?
Gunakan pd.merge_asof() untuk data dengan waktu yang tidak persis sama, tapi ingin digabungkan berdasarkan waktu terdekat.



Langkah 3: Eksekusi Penggabungan dengan Parameter yang Benar 🔧
- Kolom waktu berbeda nama?
Gunakan parameter left_on dan right_on untuk menunjuk kolom waktu yang berbeda.

- Parameter direction di merge_asof
    - backward (default): cari data terakhir sebelum waktu kejadian (paling umum).
    - forward: cari data pertama setelah waktu kejadian.
    - nearest: cari data waktu paling dekat, tanpa memedulikan sebelum atau sesudah 



Langkah 4: Validasi dan Analisis Lanjutan 📊

Periksa hasil penggabungan
Cek beberapa baris pertama dan terakhir dengan .head() dan .tail(). Pastikan hasil logis.

Lanjutkan analisis
Gunakan .query(), .groupby(), dan fungsi agregasi lainnya untuk menarik insight dari data gabungan.