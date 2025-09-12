File-file tersebut secara sistematis mempelajari cara menganalisis dan memodelkan berbagai jenis data menggunakan distribusi probabilitas yang berbeda:



1. Distribusi Normal (File: 1The_Normal_distribution.ipynb)

- Apa itu: Ini adalah distribusi probabilitas kontinu yang paling umum, sering disebut "kurva lonceng". Digunakan untuk memodelkan data yang nilainya cenderung terkonsentrasi di sekitar rata-rata.

- Implementasi Teknis:

        Membuat histogram untuk memvisualisasikan distribusi data penjualan (amir_deals['amount'].hist()).

        Menghitung probabilitas suatu peristiwa terjadi dalam rentang nilai tertentu menggunakan Cumulative Distribution Function (norm.cdf). Contohnya, menghitung probabilitas penjualan di bawah $7500.

        Menentukan nilai pada persentil tertentu menggunakan Percent Point Function (norm.ppf). Contohnya, mencari nilai penjualan yang membatasi 25% terbawah.

        Mensimulasikan data baru berdasarkan mean dan standar deviasi yang ditentukan (norm.rvs).

- Skenario Nyata: Bayangkan Anda adalah manajer penjualan Amir. Setiap bulan, Anda menetapkan target penjualan. Bagaimana Anda tahu target yang Anda berikan itu wajar, terlalu mudah, atau terlalu sulit?

        Apa yang Anda Lakukan: Anda melihat data penjualan Amir selama setahun terakhir. Anda menemukan rata-rata penjualannya adalah $5000 dengan sebaran (standar deviasi) $2000. Datanya membentuk "kurva lonceng" yang khas.

        Pertanyaan Bisnis: "Seberapa besar kemungkinan Amir bisa mencapai penjualan di atas $7500 bulan ini?"

        Guna Kode: Daripada menebak-nebak, Anda menggunakan norm.cdf(7500, 5000, 2000). Kode ini menghitung probabilitasnya berdasarkan data historis. Jika hasilnya menunjukkan probabilitas 11%, Anda tahu bahwa target $7500 adalah target yang ambisius tapi mungkin tercapai. Jika probabilitasnya hanya 1%, mungkin target itu tidak realistis.

- Intinya: Distribusi Normal membantu Anda mengukur kewajaran suatu peristiwa (seperti target penjualan) berdasarkan data masa lalu.


2. Teorema Limit Pusat / Central Limit Theorem (CLT) (File: 2The_central_limit_theorem.ipynb) (Mendapatkan Gambaran Besar dari Sampel Kecil sampling)

- Apa itu: Teorema ini menyatakan bahwa jika Anda mengambil banyak sampel acak dari populasi mana pun (terlepas dari distribusinya), distribusi dari rata-rata sampel tersebut akan mendekati distribusi normal.

- Implementasi Teknis:

        Mengambil sampel berulang kali (misalnya 100 kali) dari sebuah set data (amir_deals['num_users']).

        Menghitung rata-rata dari setiap sampel tersebut dan menyimpannya.

        Membuat histogram dari kumpulan rata-rata sampel. Hasilnya menunjukkan bahwa distribusi rata-rata sampel ini berbentuk lonceng (normal), meskipun distribusi data aslinya mungkin tidak normal.

        Membuktikan bahwa rata-rata dari semua rata-rata sampel (mean of sample_means) sangat mendekati rata-rata populasi asli.

- Skenario Nyata: Anda adalah seorang analis di sebuah perusahaan yang ingin mengetahui rata-rata kepuasan pelanggan di seluruh Indonesia. Mustahil dan sangat mahal untuk menyurvei jutaan pelanggan.

        Apa yang Anda Lakukan: Anda tidak menyurvei semua orang. Sebaliknya, Anda mengambil beberapa kelompok kecil (sampel), misalnya 100 kelompok yang masing-masing terdiri dari 20 pelanggan, lalu menghitung rata-rata kepuasan dari setiap kelompok.

        Pertanyaan Bisnis: "Bagaimana cara saya yakin bahwa rata-rata dari sampel-sampel kecil ini mewakili rata-rata seluruh pelanggan di Indonesia?"

        Guna Kode: Kode yang mengambil sampel berulang-ulang dan menghitung rata-ratanya mendemonstrasikan Teorema Limit Pusat. Teorema ini secara ajaib menjamin bahwa rata-rata dari semua rata-rata sampel Anda akan sangat mendekati rata-rata sebenarnya dari seluruh populasi. Inilah prinsip di balik quick count pemilu dan survei pasar yang akurat.

- Intinya: CLT memungkinkan kita membuat kesimpulan yang andal tentang populasi besar hanya dengan melihat sebagian kecil darinya, menghemat waktu dan biaya.


3. Distribusi Poisson (File: 3The_poisson_distribution.ipynb) (Memprediksi Jumlah Kejadian 📈)

- Apa itu: Ini adalah distribusi probabilitas diskrit yang digunakan untuk memodelkan jumlah kejadian (misalnya, jumlah email yang diterima) dalam suatu interval waktu atau ruang yang tetap, dengan rata-rata laju kejadian (λ) yang diketahui.

- Implementasi Teknis:

        Menghitung probabilitas untuk mendapatkan jumlah keberhasilan yang tepat (misalnya, tepat 5 respons) menggunakan Probability Mass Function (poisson.pmf).

        Menghitung probabilitas untuk mendapatkan jumlah keberhasilan hingga batas tertentu (misalnya, 2 respons atau kurang) menggunakan Cumulative Distribution Function (poisson.cdf).

        Menghitung probabilitas untuk mendapatkan jumlah keberhasilan di atas batas tertentu dengan menggunakan 1 - poisson.cdf.

- Skenario Nyata: Anda adalah manajer operasional sebuah call center. Rata-rata, tim Anda menerima 4 panggilan per jam. Anda perlu membuat jadwal kerja untuk besok.

        Apa yang Anda Lakukan: Anda perlu mengantisipasi jam sibuk.

        Pertanyaan Bisnis: "Berapa kemungkinan besok akan ada 10 panggilan masuk dalam satu jam? Apakah saya perlu staf tambahan?"

        Guna Kode: Anda menggunakan poisson.pmf(10, 4) atau 1 - poisson.cdf(9, 4) untuk menghitung probabilitas ini. Jika kemungkinannya sangat kecil (misalnya 0.5%), Anda mungkin tidak perlu khawatir. Tapi jika kemungkinannya cukup besar (misalnya 15%), Anda sebaiknya menyiapkan staf cadangan untuk jam tersebut agar pelanggan tidak menunggu lama.

- Intinya: Distribusi Poisson membantu memprediksi jumlah kejadian dalam interval waktu tertentu, sangat berguna untuk perencanaan sumber daya (staf, stok, dll.).


4. Distribusi Eksponensial (File: 4More_probability_distributions.ipynb) (Memprediksi Waktu Antar Kejadian ☕)

- Apa itu: Ini adalah distribusi probabilitas kontinu yang digunakan untuk memodelkan waktu antara dua kejadian dalam sebuah proses Poisson. Jika jumlah kejadian per jam mengikuti distribusi Poisson, maka waktu antar kejadian tersebut mengikuti distribusi Eksponensial.

- Implementasi Teknis:

        Menghitung probabilitas bahwa waktu tunggu hingga kejadian berikutnya kurang dari atau antara nilai tertentu.

        Menggunakan Cumulative Distribution Function (expon.cdf) dengan parameter scale, yang merupakan kebalikan dari laju rata-rata (scale=1/λ). Dalam kasus ini, rata-rata waktu respons adalah 2.5 jam.

        Secara keseluruhan, materi ini mengajarkan cara beralih dari sekadar melihat data mentah menjadi mampu memodelkannya secara statistik, menghitung probabilitas, dan memahami perilaku acak menggunakan perangkat lunak (Python dan pustaka scipy.stats).

- Skenario Nyata: Lanjutan dari contoh call center di atas. Jika rata-rata ada 4 panggilan per jam, berarti rata-rata ada 1 panggilan setiap 15 menit.

        Apa yang Anda Lakukan: Anda ingin memberi waktu istirahat yang cukup bagi staf tanpa mengorbankan layanan.

        Pertanyaan Bisnis: "Seberapa besar kemungkinan telepon akan berdering dalam 5 menit ke depan?" atau "Apakah aman bagi seorang staf untuk istirahat selama 10 menit tanpa ada panggilan masuk?"

        Guna Kode: Kode seperti expon.cdf(5, scale=15) membantu Anda menjawab ini. Ini menghitung probabilitas waktu antar kejadian. Jika probabilitas tidak ada panggilan selama 10 menit cukup tinggi, maka staf bisa mengambil istirahat singkat dengan tenang.

Intinya: Jika Poisson menghitung "berapa banyak", Eksponensial menghitung "berapa lama lagi sampai kejadian berikutnya".


Singkatnya, semua analisis teknis ini adalah cara untuk mengubah data mentah menjadi wawasan praktis untuk pengambilan keputusan di dunia nyata.







