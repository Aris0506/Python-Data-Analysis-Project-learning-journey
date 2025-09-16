## Ringkasan Teknis
Kedua file tersebut mendemonstrasikan cara mengukur dan memvisualisasikan hubungan antara berbagai variabel dalam dataset "world_happiness" menggunakan Python.

Visualisasi Hubungan: Kode tersebut menggunakan scatterplot dari library seaborn untuk membuat diagram tebar. Diagram ini adalah cara visual untuk melihat pola hubungan antara dua variabel. Misalnya, antara "skor kebahagiaan" (happiness_score) dan "harapan hidup" (life_exp).

Mengukur Kekuatan Hubungan: Untuk mendapatkan nilai kuantitatif dari hubungan tersebut, digunakan fungsi .corr(). Fungsi ini menghitung koefisien korelasi Pearson, yang nilainya berkisar antara -1 hingga +1.

    Nilai mendekati +1 menunjukkan hubungan positif yang kuat (jika satu variabel naik, yang lain cenderung naik).

    Nilai mendekati -1 menunjukkan hubungan negatif yang kuat (jika satu variabel naik, yang lain cenderung turun).

    Nilai mendekati 0 menunjukkan tidak ada hubungan linier.

Batasan Korelasi (Caveats): File kedua (2Correlation_caveats.ipynb) menyoroti keterbatasan korelasi.

    Hubungan Non-Linier: Korelasi hanya efektif untuk mengukur hubungan linier (yang terlihat seperti garis lurus). Pada kasus gdp_per_cap dan life_exp, hubungannya tidak lurus. Untuk mengatasinya, dilakukan transformasi logaritmik (np.log) pada gdp_per_cap agar hubungannya menjadi lebih linier dan korelasinya lebih akurat.

    Korelasi Bukan Sebab-Akibat: Ditekankan bahwa korelasi tinggi tidak berarti satu variabel menyebabkan perubahan pada variabel lain. Contohnya pada grams_sugar_per_day dan happiness_score, meskipun mungkin ada korelasi, bukan berarti konsumsi gula secara langsung menyebabkan kebahagiaan. Bisa jadi ada faktor lain yang memengaruhi keduanya.


## Desain Eksperimen
bertujuan untuk menentukan hubungan sebab-akibat antara 

perlakuan (treatment) dan respons (response).

Eksperimen Terkontrol: Peneliti membagi partisipan menjadi kelompok perlakuan (yang menerima intervensi) dan kelompok kontrol (yang tidak). Kunci utamanya adalah membuat kedua kelompok sebanding untuk menghindari bias.

Standar Emas Eksperimen:
    - Randomized Controlled Trial (RCT): Partisipan ditempatkan secara acak ke dalam kelompok untuk memastikan perbandingan yang adil.
    - Plasebo: Kelompok kontrol menerima "perlakuan palsu" (seperti pil gula) agar mereka tidak tahu berada di kelompok mana. Ini untuk memastikan efek yang muncul benar-benar dari perlakuan, bukan sugesti.
    - Double-Blind Trial: Baik partisipan maupun peneliti tidak tahu siapa yang menerima perlakuan asli atau plasebo. Ini mencegah bias dalam penilaian hasil

Studi Observasional: Peneliti hanya mengamati tanpa memberikan perlakuan. Partisipan mengelompokkan diri mereka sendiri (misalnya, perokok dan non-perokok). Studi ini hanya bisa menunjukkan

asosiasi, bukan sebab-akibat, karena rentan terhadap variabel perancu.





## Implementasi di Kehidupan Nyata
Analisis korelasi sangat umum digunakan dalam berbagai bidang untuk pengambilan keputusan berdasarkan data.

    Bisnis dan Pemasaran: 📈 Sebuah perusahaan e-commerce dapat menganalisis korelasi antara jumlah uang yang dihabiskan untuk iklan di media sosial dengan jumlah penjualan produk. Jika ditemukan korelasi positif yang kuat, mereka dapat memutuskan untuk meningkatkan anggaran iklan untuk menaikkan penjualan.

    Kesehatan dan Medis: 🩺 Para peneliti medis bisa mempelajari korelasi antara jumlah jam tidur rata-rata per malam dengan tingkat tekanan darah. Jika ditemukan korelasi negatif (semakin sedikit tidur, semakin tinggi tekanan darah), ini bisa menjadi dasar untuk kampanye kesehatan yang mendorong pentingnya tidur cukup.

    Keuangan dan Investasi: 💰 Seorang analis keuangan dapat menguji korelasi antara harga saham sebuah perusahaan teknologi dengan harga indeks saham teknologi secara keseluruhan (misalnya, Nasdaq). Korelasi yang sangat tinggi menunjukkan bahwa harga saham perusahaan tersebut cenderung bergerak mengikuti tren pasar secara umum.

    Operasional Pabrik: 🏭 Manajer pabrik dapat menganalisis korelasi antara suhu mesin produksi dengan jumlah produk cacat yang dihasilkan. Jika ada korelasi positif, mereka tahu bahwa menjaga suhu mesin tetap rendah adalah kunci untuk mengurangi produk gagal.

## materi pembelajaran ini disertai mini project correlation 