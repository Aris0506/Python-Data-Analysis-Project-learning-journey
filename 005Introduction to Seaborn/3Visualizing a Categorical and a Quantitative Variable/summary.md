Secara singkat, file-file tersebut mempelajari cara membuat dan menyesuaikan berbagai jenis visualisasi data kategorikal menggunakan library Seaborn di Python. Fokus utamanya adalah pada fungsi seaborn.catplot() yang serbaguna untuk membandingkan distribusi data di antara berbagai kategori.


Rangkuman Teknis
Anda sedang mempelajari cara untuk memvisualisasikan hubungan antara variabel kategorikal (seperti "tipe produk" atau "tingkat pendidikan") dengan variabel numerik (seperti "harga" atau "nilai ujian").


Count Plots & Bar Plots (1_count_plots_and_bar_plots.ipynb):

Tujuan: Menghitung frekuensi setiap kategori (count plot) atau menunjukkan tendensi sentral (seperti rata-rata atau median) dari data numerik untuk setiap kategori (bar plot).

Kustomisasi: Anda belajar mengubah orientasi plot, mengurutkan kategori (order), membuat sub-plot berdasarkan kategori lain (col), dan menghilangkan confidence interval (ci=None).



Box Plots (2_Box_plots.ipynb):

Tujuan: Memahami distribusi data numerik pada setiap kategori. Box plot menampilkan median (garis tengah), kuartil (kotak), rentang data (kumis/whiskers), dan nilai-nilai ekstrem (outliers).

Kustomisasi: Anda belajar mengatur urutan kategori (order), menyembunyikan outliers (sym=""), dan menyesuaikan panjang "kumis" untuk merepresentasikan rentang data yang berbeda (misalnya, persentil ke-5 dan ke-95 dengan whis=[5, 95]).



Point Plots (3_Point_plots.ipynb):

Tujuan: Mirip dengan bar plot, point plot menunjukkan estimasi tendensi sentral (misalnya, rata-rata) dan confidence interval-nya. Plot ini sangat efektif untuk membandingkan tren di antara berbagai grup.

Kustomisasi: Anda belajar menambahkan penanda pada confidence interval (capsize), memisahkan garis antar titik (join=False), membagi data menjadi sub-grup berdasarkan warna (hue), dan mengubah fungsi estimasi dari rata-rata menjadi median (estimator=median).



Implementasi di Kehidupan Nyata
Berikut adalah contoh penerapan yang sederhana dan tidak terlalu teknikal:




📊 Count Plot & Bar Plot: Analisis Restoran
Masalah: Seorang manajer restoran ingin tahu menu mana yang paling banyak dipesan dan menu mana yang memberikan rating kepuasan pelanggan tertinggi.

Implementasi:

Count Plot: Gunakan count plot untuk menghitung jumlah pesanan untuk setiap menu (misalnya, "Nasi Goreng", "Sate Ayam", "Gado-gado"). Ini akan langsung menunjukkan menu terlaris.

Bar Plot: Gunakan bar plot untuk menunjukkan rata-rata rating (dari skala 1-5) untuk setiap menu. Manajer bisa melihat menu mana yang disukai pelanggan, meskipun mungkin bukan yang paling sering dipesan.




📦 Box Plot: Analisis Harga Properti
Masalah: Sebuah agen properti ingin membandingkan harga rumah di berbagai kompleks perumahan di sebuah kota.

Implementasi: Gunakan box plot. Setiap "kompleks perumahan" menjadi kategori di sumbu X, dan "harga rumah" di sumbu Y.

Manfaat: Agen bisa dengan cepat melihat:

Median harga di setiap kompleks (garis di tengah kotak).

Rentang harga mayoritas rumah (panjang kotak).

Apakah ada rumah dengan harga sangat mahal atau murah (outliers) dibandingkan rumah lain di kompleks yang sama.




📈 Point Plot: Efektivitas Kampanye Marketing
Masalah: Sebuah perusahaan ingin membandingkan efektivitas dua kampanye iklan digital (misalnya, Iklan A vs. Iklan B) terhadap jumlah klik harian selama seminggu.

Implementasi: Gunakan point plot. "Hari" (Senin, Selasa, dst.) berada di sumbu X, "jumlah klik" di sumbu Y, dan jenis iklan ("Iklan A" dan "Iklan B") dibedakan dengan warna (hue).

Manfaat: Perusahaan bisa dengan mudah membandingkan tren performa kedua iklan dari hari ke hari. Garis yang menghubungkan titik-titik akan menunjukkan apakah jumlah klik cenderung naik atau turun, dan plot mana yang secara konsisten menghasilkan klik lebih tinggi.