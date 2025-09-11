ini adalah materi pembelajaran merging and ordered time-series data berguna
untuk menggabungkan dua atau lebih set data berbasis waktu yang stempel waktunya tidak sinkron atau tidak cocok persis, 
agar bisa dianalisis secara bersamaan:

- pd.merge_asof() -> untuk data tidak sinkron
- pd.merg_ordered() -> bisa untuk mengisi nilai yang hilang
- .melt() ubah format dataset
- .query() cocok untuk analisis menjawab pertanyaan sesuai kontes menggunakan pengkondisian

## Mengatasi Data yang Tidak Sinkron (Asynchronous Data)
Ini adalah masalah paling umum dalam data time-series. Bayangkan Anda punya data transaksi saham VISA yang dicatat per jam, 
dan data saham IBM yang dicatat pada waktu acak setiap beberapa menit. Anda tidak bisa menggunakan merge biasa karena tidak ada waktu yang cocok persis.

Solusi: pd.merge_asof() digunakan untuk mengatasi ini. Fungsi ini tidak mencari kecocokan waktu yang identik, melainkan 
mencocokkan dengan waktu terdekat yang tersedia. Ini memungkinkan Anda untuk mengetahui, misalnya, "Berapa harga saham IBM tepat 
sebelum harga saham VISA dicatat pada jam 4 sore?"


## Menyiapkan Data untuk Analisis Prediktif
Tujuan tingkat lanjutnya adalah untuk menyiapkan data untuk analisis yang lebih kompleks, seperti machine learning, tanpa menyebabkan "kebocoran data".

Solusi: pd.merge_asof() ideal untuk membuat set data pelatihan. Dengan menggabungkan data fitur (misalnya, data sensor) ke data target 
(misalnya, kejadian kerusakan mesin) menggunakan direction='backward', Anda memastikan bahwa untuk setiap kejadian, 
Anda hanya menggunakan data fitur dari masa lalu. Ini meniru skenario prediksi di dunia 
nyata dan mencegah model Anda "curang" dengan melihat data dari masa depan.


## Mengisi Rumpang Waktu dan Data Hilang
Saat Anda menggabungkan dua timeline, seringkali ada "rumpang" atau kekosongan di mana satu set data memiliki catatan waktu tetapi yang lain tidak.

Solusi: pd.merge_ordered() sangat berguna untuk ini. Fungsi ini secara 
default melakukan outer join, yang mempertahankan semua baris waktu dari kedua set data, lalu secara otomatis dapat mengisi nilai yang hilang (NaN). 
Contoh paling umum adalah menggunakan metode 
ffill (forward fill), yang mengisi kekosongan dengan nilai terakhir yang diketahui. Tujuannya adalah untuk menciptakan satu timeline yang berkelanjutan dan lengkap.

####
Pada dasarnya, bab ini menjawab pertanyaan: "Bagaimana cara saya menghubungkan data kejadian A dengan data kondisi B, 
jika keduanya tidak terjadi pada waktu yang benar-benar sama?"

