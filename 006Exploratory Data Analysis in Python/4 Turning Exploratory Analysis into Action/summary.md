Inti dari file-file tersebut adalah mempelajari proses Exploratory Data Analysis (EDA) atau Analisis Data Eksplorasi. Ini adalah langkah awal yang krusial dalam setiap proyek data, di mana tujuannya adalah untuk memahami isi data, menemukan pola, anomali, dan hubungan antar variabel, serta merumuskan pertanyaan (hipotesis) sebelum melakukan pemodelan statistik yang lebih kompleks.



Secara Teknis, Ini yang Sedang Dilakukan:
Singkatnya, materi ini mengajarkan cara "menginterogasi" sebuah dataset (dalam contoh ini, data gaji para profesional data) menggunakan library Python seperti Pandas dan Seaborn.

Analisis Fitur Kategorikal (Categorical Feature Analysis):

Tujuan: Memahami variabel yang bukan angka, seperti "Jabatan" (Job_Category) atau "Ukuran Perusahaan" (Company_Size).

Teknik:

value_counts(normalize=True): Untuk melihat distribusi atau frekuensi setiap kategori. Misalnya, melihat persentase jumlah Data Scientist dibandingkan Data Analyst. Ini penting untuk mendeteksi 

class imbalance (apakah ada kategori yang sangat dominan?). 

pd.crosstab(): Untuk melihat hubungan antara dua variabel kategori. Misalnya, membandingkan jumlah karyawan dengan tingkat pengalaman (Experience) di berbagai ukuran perusahaan (Company_Size). Fungsi ini juga bisa digunakan untuk menghitung rata-rata nilai numerik (seperti 

Salary_USD) untuk setiap kombinasi kategori. 



Rekayasa Fitur (Feature Engineering):

Tujuan: Menciptakan variabel (fitur) baru dari data yang sudah ada untuk mendapatkan wawasan yang lebih dalam.

Teknik:

Ekstraksi dari Tanggal: Mengambil informasi spesifik dari kolom tanggal, seperti bulan (.dt.month) atau hari dalam seminggu (.dt.weekday), untuk melihat apakah ada pola temporal (misalnya, apakah gaji dipengaruhi oleh waktu respons survei).

Binning atau Kategorisasi: Mengubah variabel numerik (seperti Salary_USD) menjadi variabel kategori (salary_level). Ini dilakukan dengan menentukan rentang (misalnya, berdasarkan persentil 25%, 50%, 75%) dan memberinya label seperti "entry", "mid", "senior". Fungsi yang digunakan adalah pd.cut(). 




Analisis Korelasi (Correlation Analysis):

Tujuan: Mengukur seberapa kuat hubungan linear antara dua variabel numerik.

Teknik: salaries.corr() dihitung dan divisualisasikan menggunakan sns.heatmap(). Heatmap memudahkan kita melihat secara cepat variabel mana yang memiliki korelasi kuat (positif atau negatif). 




Visualisasi untuk Hipotesis (Visualization for Hypotheses):

Tujuan: Menggunakan grafik untuk membandingkan grup-grup dalam data dan merumuskan hipotesis (dugaan awal).

Teknik:
sns.barplot(): Membandingkan nilai rata-rata suatu variabel numerik (misal, Salary_USD) di antara kategori yang berbeda (misal, Company_Size atau Employee_Location). 

sns.countplot(): Menghitung dan memvisualisasikan jumlah data di setiap kategori, seringkali dipisahkan oleh kategori lain (hue). 




Implementasi di Kehidupan Nyata (Contoh: Toko Online)
Bayangkan Anda adalah pemilik toko sepatu online dan Anda baru saja mengunduh data penjualan selama setahun terakhir. Apa yang bisa Anda lakukan dengan teknik-teknik di atas?

1. Memahami Produk & Pelanggan (Analisis Kategorikal)

Anda bisa menggunakan value_counts() untuk menjawab: "Merek sepatu apa yang paling laris?" atau "Ukuran sepatu mana yang paling sering habis?". Ini membantu Anda mengatur stok barang.

Dengan pd.crosstab(), Anda bisa bertanya: "Apakah pelanggan di kota Jakarta cenderung membeli sepatu lari, sementara pelanggan di Bandung lebih suka sneakers?". Ini membantu strategi pemasaran lokal Anda.

2. Menciptakan Wawasan Baru (Rekayasa Fitur)

Dari kolom tanggal_pembelian, Anda bisa mengekstrak bulan untuk melihat "Kapan puncak penjualan terjadi? Apakah saat musim liburan atau menjelang tahun ajaran baru?". Ini membantu Anda merencanakan promosi.

Dengan pd.cut() pada kolom harga_sepatu, Anda bisa mengelompokkan produk menjadi "Ekonomis", "Standar", dan "Premium". Lalu Anda bisa melihat kelompok produk mana yang paling diminati oleh pelanggan pria vs. wanita.

3. Mencari Hubungan Tersembunyi (Analisis Korelasi)

Anda bisa membuat heatmap untuk melihat apakah ada hubungan antara jumlah_barang_di_keranjang dengan total_belanja. Jika korelasinya kuat, mungkin Anda bisa menawarkan diskon ongkir untuk pembelian dalam jumlah tertentu.

4. Merumuskan Strategi Bisnis (Visualisasi untuk Hipotesis)

Anda membuat barplot untuk membandingkan rata-rata belanja antara member dan non-member. Jika rata-rata belanja member jauh lebih tinggi, Anda bisa merumuskan hipotesis: "Program membership efektif meningkatkan loyalitas dan nilai belanja pelanggan." Langkah selanjutnya adalah membuktikan hipotesis ini secara statistik.







Apakah Ini Bisa Menjadi Template Default?
Ya, tentu saja. Proses yang dijelaskan dalam file-file ini adalah template fundamental dan standar emas dalam dunia data. Ini adalah langkah pertama yang wajib dilakukan di hampir semua proyek analisis data atau machine learning.

Mengapa ini menjadi default?

- Mencegah Kesalahan Fatal: Menganalisis data tanpa EDA ibarat membangun rumah tanpa memeriksa kondisi tanahnya. Anda bisa saja membangun model machine learning yang canggih, tapi jika datanya salah, tidak lengkap, atau penuh anomali, model Anda tidak akan berguna.

- Memberi Konteks: EDA memberikan Anda "rasa" terhadap data tersebut. Anda jadi paham konteksnya, apa saja keunikannya, dan di mana saja potensi masalahnya.

- Mengarahkan Analisis: Hasil dari EDA (visualisasi dan hipotesis awal) akan menjadi pemandu untuk langkah selanjutnya. Anda jadi tahu analisis statistik atau model apa yang paling relevan untuk digunakan.

- Analogi sederhananya: EDA adalah seperti seorang dokter yang melakukan pemeriksaan umum (cek suhu, tekanan darah, bertanya keluhan) pada pasien sebelum memutuskan untuk melakukan tes yang lebih spesifik dan mahal seperti MRI atau CT scan. Ini adalah langkah diagnostik awal yang tidak bisa dilewati.
