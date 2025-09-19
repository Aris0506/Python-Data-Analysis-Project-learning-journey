ini adalah rangkuman dari ketiga file notebook tersebut.

Intinya, file-file tersebut mempelajari cara membuat visualisasi data relasional menggunakan pustaka (library) Seaborn di Python. Fokus utamanya adalah pada fungsi sns.relplot() untuk memahami hubungan antara dua atau lebih variabel data.

## Rangkuman Teknis
Pembelajaran dalam notebook-notebook ini dibagi menjadi tiga tahap utama:

Plot Relasional Dasar dan Subplots: Notebook pertama memperkenalkan fungsi inti sns.relplot(). Anda belajar cara membuat plot sebar (scatter plot) untuk melihat korelasi antara dua variabel (misalnya, absensi siswa vs. nilai akhir). Fitur utamanya adalah kemampuan untuk memecah visualisasi menjadi beberapa plot kecil dalam satu gambar (disebut subplots atau facets) menggunakan parameter col (untuk kolom) dan row (untuk baris), sehingga memudahkan perbandingan antar kategori yang berbeda.

Kustomisasi Plot Sebar: Notebook kedua berfokus pada penambahan dimensi informasi pada satu plot. Anda belajar cara memvisualisasikan variabel ketiga atau keempat dengan mengubah atribut visual dari titik data. Parameter yang digunakan adalah:

    hue: Mengubah warna titik berdasarkan kategori (misalnya, warna berbeda untuk mobil dari negara asal yang berbeda).

    size: Mengubah ukuran titik berdasarkan nilai numerik (misalnya, ukuran titik lebih besar untuk mobil dengan silinder lebih banyak).

    style: Mengubah bentuk penanda (marker) berdasarkan kategori (misalnya, lingkaran untuk mobil AS, silang untuk Eropa).

Plot Garis (Line Plots): Notebook ketiga memperkenalkan jenis plot relasional lainnya, yaitu kind="line". Plot ini sangat ideal untuk menampilkan tren dari data yang berkelanjutan, seperti perubahan dari waktu ke waktu (misalnya, efisiensi bahan bakar mobil per tahun model). Di sini Anda juga belajar untuk:

Menampilkan ketidakpastian atau variasi data dengan ci="sd" (menunjukkan standar deviasi sebagai area bayangan di sekitar garis).

Membuat beberapa garis dalam satu plot untuk membandingkan subgrup yang berbeda, menggunakan parameter hue dan style seperti pada scatter plot.

Secara keseluruhan, Anda belajar untuk beralih dari plot sederhana ke visualisasi data yang kaya informasi dan mudah ditafsirkan menggunakan satu fungsi utama, yaitu seaborn.relplot().

## Implementasi di Kehidupan Nyata (Contoh Non-Teknis)
Bayangkan Anda adalah manajer sebuah jaringan kedai kopi yang memiliki beberapa cabang di kota yang berbeda. Anda ingin memahami pola penjualan. Anda bisa menggunakan konsep dari notebook ini untuk:

    Melihat Hubungan Dasar: Anda membuat plot sederhana untuk melihat hubungan antara suhu harian (sumbu x) dan jumlah es kopi yang terjual (sumbu y). Anda mungkin menemukan bahwa semakin panas cuacanya, semakin banyak es kopi yang terjual. Ini seperti sns.relplot(kind="scatter").

    Menambah Detail pada Plot: Sekarang, Anda ingin tahu lebih banyak. Pada plot yang sama, Anda bisa:

    Memberi warna (hue) yang berbeda untuk setiap cabang (misalnya, biru untuk Jakarta, hijau untuk Bandung).

    Mengubah ukuran (size) titik berdasarkan total pendapatan hari itu.

    Menggunakan bentuk (style) yang berbeda jika pada hari itu ada promo (misalnya, bintang jika ada promo, lingkaran jika tidak).

    Dengan satu gambar, Anda bisa langsung melihat bahwa "Cabang Jakarta (biru) menjual banyak es kopi saat cuaca panas, dan titik-titiknya besar-besar (pendapatan tinggi), terutama yang berbentuk bintang (saat ada promo)".

    Melihat Tren Sepanjang Waktu: Anda ingin melihat tren penjualan Hot Latte selama setahun terakhir. Anda bisa membuat plot garis (kind="line") dengan bulan (sumbu x) dan rata-rata penjualan harian (sumbu y). Anda juga bisa menambahkan garis terpisah dengan warna berbeda (hue) untuk setiap cabang.

    Hasilnya, Anda bisa melihat bahwa "Penjualan Hot Latte di cabang Bandung (hijau) cenderung naik di musim hujan, sementara di cabang Jakarta (biru) relatif stabil sepanjang tahun." Area bayangan di sekitar garis (ci="sd") akan menunjukkan seberapa fluktuatif penjualan di setiap cabang.







