Secara teknis, file-file tersebut mempelajari cara membuat visualisasi data menggunakan Python dengan library Seaborn dan Pandas. Fokus utamanya adalah membuat plot statistik yang informatif dari berbagai jenis data.


## Rangkuman Teknis

- Dasar Visualisasi dengan Seaborn: Anda mempelajari cara membuat plot dasar seperti scatterplot (untuk melihat hubungan antara dua variabel numerik) dan countplot (untuk menghitung frekuensi data kategorikal). Awalnya, plot ini dibuat dari daftar (list) Python sederhana.

- Integrasi dengan Pandas: Selanjutnya, pembelajaran beralih ke penggunaan library Pandas untuk membaca data dari file (seperti CSV) ke dalam sebuah struktur yang disebut DataFrame. DataFrame ini kemudian menjadi sumber data utama untuk plot Seaborn, yang memungkinkan Anda merujuk kolom data secara langsung berdasarkan namanya (misalnya, x="Spiders"). Ini adalah praktik umum dan lebih efisien untuk analisis data.

- Menambah Dimensi dengan hue: Pembelajaran berlanjut ke teknik yang lebih canggih, yaitu menambahkan variabel ketiga ke dalam plot menggunakan parameter hue. Parameter ini secara otomatis membedakan data berdasarkan kategori variabel tersebut dengan warna yang berbeda. Anda juga belajar cara mengkustomisasi visualisasi ini, seperti mengubah urutan legenda (hue_order) dan menentukan palet warna (palette).

Intinya, Anda sedang belajar alur kerja dasar seorang analis data: memuat data menggunakan Pandas, lalu memvisualisasikannya dengan Seaborn untuk menemukan pola dan wawasan.

## Implementasi di Kehidupan Nyata
Berikut adalah beberapa contoh penerapan praktis dari apa yang sedang Anda pelajari:

   1. Analisis Penjualan di Toko Online (Scatter Plot & Hue)
    Anda bisa membuat scatterplot untuk melihat hubungan antara biaya iklan (sumbu x) dan jumlah penjualan (sumbu y). Kemudian, Anda dapat menambahkan parameter hue untuk membedakan berdasarkan kategori produk (misalnya, "Elektronik" vs. "Pakaian"). Dari sini, Anda mungkin menemukan bahwa menaikkan biaya iklan sangat efektif untuk penjualan elektronik, tetapi tidak terlalu berdampak pada penjualan pakaian.

   2. Survei Kepuasan Pelanggan (Count Plot)
    Sebuah perusahaan telekomunikasi bisa menggunakan countplot untuk menghitung jumlah pelanggan di setiap wilayah atau kota. Ini membantu manajemen untuk melihat secara cepat di mana basis pelanggan terbesar mereka berada dan mengalokasikan sumber daya (seperti teknisi atau tim marketing) dengan lebih baik.

   3. Analisis Data Siswa di Sekolah (Scatter Plot & Hue)
    Seorang kepala sekolah bisa menggunakan scatterplot untuk menganalisis hubungan antara jumlah absensi siswa (sumbu x) dan nilai akhir mereka (sumbu y). Dengan menambahkan hue untuk membedakan antara siswa yang tinggal di "Pedesaan" dan "Perkotaan", sekolah bisa mengetahui apakah ada tren yang berbeda antara kedua kelompok tersebut dan mungkin perlu memberikan dukungan tambahan untuk salah satu kelompok.