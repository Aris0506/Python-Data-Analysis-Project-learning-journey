Tentu, mari kita rangkum.

Secara singkat, file-file tersebut mempelajari proses fundamental dalam analisis data yang disebut Exploratory Data Analysis (EDA), dengan fokus utama pada pembersihan data (data cleaning) dan rekayasa fitur (feature engineering). Ini adalah langkah-langkah persiapan yang krusial sebelum data dapat digunakan untuk analisis lebih lanjut atau untuk membuat model machine learning.


Rangkuman Teknis (Apa yang Sedang Dilakukan)
Proses yang dipelajari adalah alur kerja sistematis untuk mengubah data mentah yang "berantakan" menjadi data yang "bersih" dan informatif.



Menangani Data yang Hilang (Missing Data):

Tujuan: Mengidentifikasi dan mengatasi data yang kosong atau tidak lengkap dalam dataset.

Proses:

Menghitung jumlah nilai yang hilang di setiap kolom menggunakan .isna().sum().

Menetapkan ambang batas (misalnya 5% dari total data). Jika kolom memiliki data hilang di bawah ambang batas ini, baris yang mengandung data hilang tersebut akan dihapus (.dropna()).

Untuk kolom dengan data hilang di atas ambang batas (dalam contoh ini, kolom Price), dilakukan imputasi. Nilai yang hilang diisi dengan nilai statistik yang relevan, seperti median harga berdasarkan grupnya (misalnya, mengisi harga tiket yang hilang dengan median harga dari maskapai/Airline yang sama).




Mengolah Data Kategorikal:

Tujuan: Menyederhanakan dan mengelompokkan data teks (objek/string) agar lebih mudah dianalisis.

Proses:

Mengidentifikasi kolom mana yang berisi teks (.select_dtypes("object")).

Kolom dengan terlalu banyak nilai unik (seperti Duration dengan format "2h 50m") sulit untuk divisualisasikan.

Dibuatlah kategori baru (Duration_Category) berdasarkan pola dalam teks menggunakan .str.contains() dan np.select(). Contohnya, semua durasi antara "0h" hingga "4h" dikelompokkan ke dalam kategori "Short-haul".




Mengolah Data Numerik & Rekayasa Fitur:

Tujuan: Memastikan data angka bisa diolah secara matematis dan menciptakan fitur (kolom) baru yang lebih bermakna.

Proses:

Membersihkan kolom angka yang masih dalam format teks (misalnya, mengubah "2h" menjadi angka 2.0 dengan .str.replace() dan .astype(float)).

Rekayasa Fitur: Membuat kolom baru yang berisi informasi statistik dari grup data lain. Contohnya, membuat kolom airline_price_st_dev yang isinya adalah standar deviasi harga untuk setiap maskapai. Ini dilakukan dengan groupby().transform(), yang memungkinkan perhitungan statistik per grup tanpa mengubah bentuk asli data.





Menangani Outlier (Data Anomali):

Tujuan: Mengidentifikasi dan menghapus nilai-nilai ekstrem yang dapat mengganggu hasil analisis atau performa model.

Proses:

Menggunakan metode Interquartile Range (IQR).

Menghitung kuartil pertama (25%) dan kuartil ketiga (75%).

Menentukan batas atas (kuartil_ketiga + 1.5 * IQR) dan batas bawah (kuartil_pertama - 1.5 * IQR).

Data yang berada di luar rentang batas ini dianggap sebagai outlier dan dihapus dari dataset.



Implementasi di Kehidupan Nyata (Contoh Non-Teknis)
Bayangkan Anda adalah manajer sebuah platform e-commerce (seperti Tokopedia atau Shopee) dan ingin menganalisis data penjualan untuk meningkatkan strategi marketing. Data mentah yang Anda dapatkan sangat berantakan.

Menangani Data Hilang: Ada beberapa produk yang terdaftar tanpa harga. Menghapus produk ini akan menghilangkan informasi penjualan. Sebaliknya, Anda melakukan imputasi: untuk sebuah "kaos pria" yang harganya kosong, Anda mengisinya dengan harga median dari semua produk lain dalam kategori "kaos pria". Ini jauh lebih akurat daripada mengisinya dengan rata-rata harga seluruh produk (yang bisa jadi termasuk harga laptop).

Mengolah Data Kategorikal: Kolom "Nama Produk" sangat bervariasi ("Kaos Polos Hitam Pria Lengan Pendek", "Baju Kaos Distro Keren Ukuran M"). Sulit untuk menganalisis kaos mana yang paling laku. Anda kemudian membuat kolom baru "Tipe Pakaian" dengan kategori: "Kaos", "Kemeja", "Jaket", dll. Ini membuat analisis menjadi jauh lebih sederhana.

Mengolah Data Numerik & Rekayasa Fitur: Kolom "Berat Produk" tertulis sebagai "500 gram". Anda mengubahnya menjadi 0.5 agar bisa dihitung dalam kilogram. Kemudian, Anda membuat fitur baru: "Biaya Pengiriman Rata-rata per Kategori", yang membantu Anda memutuskan kategori mana yang perlu subsidi ongkir.

Menangani Outlier: Saat menganalisis harga "mouse komputer", Anda menemukan satu produk terjual seharga Rp 20.000.000, sementara sebagian besar harganya di bawah Rp 1.000.000. Harga ekstrem ini mungkin karena salah input atau produk edisi terbatas yang sangat langka. Jika Anda ingin mengetahui harga mouse pada umumnya, outlier ini harus disisihkan agar tidak membuat rata-rata harga menjadi sangat tinggi dan menyesatkan.



Apakah Ini Template Standar dalam Proyek Data?
Ya, absolut.

Proses yang dijelaskan dalam file-file ini adalah dasar dari hampir semua proyek analisis data dan machine learning. Ini bisa dianggap sebagai template atau blueprint fundamental.

Dunia nyata jarang sekali menyediakan data yang sempurna. Sebelum seorang analis data dapat membuat laporan, visualisasi, atau model prediksi yang andal, mereka harus melalui siklus pembersihan dan persiapan ini. Mengabaikan langkah-langkah ini sama saja dengan membangun rumah di atas fondasi yang rapuh.

Analogi yang pas adalah seperti seorang koki yang melakukan mise en place. Sebelum memasak, koki akan mencuci sayuran (membersihkan data), memotongnya sesuai ukuran (mengolah kategori dan numerik), menyingkirkan bagian yang busuk (menangani outlier), dan memastikan semua bahan siap pakai. Proses persiapan ini tidak bisa dilewati jika ingin menghasilkan masakan yang lezat (analisis yang akurat).

Meskipun alat atau teknik spesifiknya dapat bervariasi tergantung pada masalahnya, filosofi dan alur kerja untuk memeriksa dan menangani data yang hilang, kategori yang berantakan, numerik yang kotor, dan outlier adalah standar universal dalam industri data.