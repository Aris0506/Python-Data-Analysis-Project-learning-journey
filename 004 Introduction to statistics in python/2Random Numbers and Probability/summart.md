Ringkasan Analisis Probabilitas dan Distribusi dalam Notebook Python

Keempat file notebook Python ini menyajikan konsep-konsep dasar probabilitas dan statistik menggunakan library scipy.stats dan numpy di Python. Analisis dimulai dari probabilitas dasar, berlanjut ke distribusi diskrit dan kontinu, dan diakhiri dengan distribusi binomial sebagai kasus khusus.



File 1: 1What_are_the_chance.ipynb - Probabilitas Dasar dan Sampling
Notebook ini memperkenalkan konsep fundamental probabilitas dan teknik sampling.

- Perhitungan Probabilitas: Kode ini mendemonstrasikan cara menghitung probabilitas empiris dari suatu peristiwa. Ini dilakukan dengan menghitung frekuensi kemunculan setiap kategori (dalam hal ini, produk dalam data amir_deals) dan membaginya dengan jumlah total pengamatan. Ini adalah pendekatan dasar untuk mengestimasi probabilitas dari data.

- Sampling: Notebook ini membedakan dua jenis teknik sampling:

- Sampling with Replacement (Pengambilan Sampel dengan Pengembalian): Setiap unit yang dipilih dari populasi dikembalikan sebelum pemilihan berikutnya. Hal ini memungkinkan unit yang sama untuk dipilih beberapa kali.

- Sampling without Replacement (Pengambilan Sampel tanpa Pengembalian): Setiap unit yang dipilih tidak dikembalikan ke populasi, sehingga setiap unit hanya dapat dipilih satu kali.

Kode ini juga menunjukkan penggunaan np.random.seed() untuk memastikan reproduktifitas hasil acak, yang penting untuk analisis yang konsisten.




File 2: 2Discrete_distribution.ipynb - Distribusi Probabilitas Diskrit
Notebook ini berfokus pada variabel acak diskrit dan distribusinya.

- Distribusi Probabilitas: Dijelaskan cara membuat distribusi probabilitas dari data diskrit. Ini dicapai dengan menghitung frekuensi relatif dari setiap nilai unik dalam kumpulan data (ukuran grup di restoran). Hasilnya adalah sebuah tabel yang memetakan setiap ukuran grup ke probabilitas kemunculannya.

- Visualisasi: Sebuah histogram digunakan untuk memvisualisasikan distribusi ukuran grup, memberikan representasi grafis dari frekuensi setiap kategori.

- Nilai Harapan (Expected Value): Kode ini mengimplementasikan perhitungan nilai harapan (E[X]) dari distribusi probabilitas diskrit. Nilai harapan dihitung sebagai jumlah dari setiap hasil yang mungkin dikalikan dengan probabilitasnya (E[X]=∑x⋅P(x)). Ini memberikan rata-rata tertimbang dari hasil yang diharapkan dalam jangka panjang.

- Probabilitas Kumulatif: Demonstraasi perhitungan probabilitas kumulatif untuk menemukan probabilitas suatu peristiwa yang mencakup beberapa hasil (misalnya, probabilitas ukuran grup 4 atau lebih) dengan menjumlahkan probabilitas masing-masing hasil tersebut.




File 3: 3Continuous_distribution.ipynb - Distribusi Probabilitas Kontinu
Notebook ini beralih ke variabel acak kontinu, dengan fokus pada Distribusi Seragam (Uniform Distribution).

- Distribusi Seragam: Distribusi ini digunakan ketika setiap hasil dalam rentang tertentu memiliki kemungkinan yang sama untuk terjadi. Contoh yang diberikan adalah waktu tunggu untuk proses back-up yang terjadi setiap 30 menit, di mana waktu tunggu dapat berkisar antara 0 hingga 30 menit dengan probabilitas yang sama.

- Fungsi Distribusi Kumulatif (CDF): Notebook ini secara ekstensif menggunakan fungsi uniform.cdf(). CDF menghitung probabilitas bahwa variabel acak akan mengambil nilai kurang dari atau sama dengan nilai tertentu. Ini digunakan untuk menghitung:

Probabilitas menunggu kurang dari waktu tertentu: P(X≤x).

Probabilitas menunggu lebih dari waktu tertentu: P(X>x), dihitung sebagai 1−P(X≤x).

Probabilitas menunggu dalam rentang waktu tertentu [a,b]: P(a≤X≤b), dihitung sebagai P(X≤b)−P(X≤a).

- Simulasi: Kode ini menggunakan uniform.rvs() untuk menghasilkan sampel acak dari distribusi seragam. Hasil simulasi (misalnya, 1000 waktu tunggu) kemudian divisualisasikan menggunakan histogram, yang seharusnya mendekati bentuk persegi panjang, karakteristik dari distribusi seragam.




File 4: 4The_binomial_distribution.ipynb - Distribusi Binomial
Notebook ini membahas Distribusi Binomial, yang merupakan distribusi probabilitas diskrit yang sangat umum.

- Karakteristik Distribusi Binomial: Distribusi ini memodelkan jumlah keberhasilan dalam sejumlah uji coba Bernoulli (n) yang independen, di mana setiap uji coba hanya memiliki dua hasil (sukses atau gagal) dan probabilitas keberhasilan (p) konstan.

- Simulasi: Fungsi binom.rvs() digunakan untuk mensimulasikan hasil dari proses binomial. Contohnya termasuk mensimulasikan satu kesepakatan penjualan, kesepakatan selama seminggu (3 uji coba), dan selama 52 minggu. Ini berguna untuk memahami variabilitas hasil dalam jangka pendek dan panjang.

- Fungsi Massa Probabilitas (PMF): Fungsi binom.pmf(k, n, p) digunakan untuk menghitung probabilitas mendapatkan tepat k keberhasilan dalam n uji coba.

- Fungsi Distribusi Kumulatif (CDF): Fungsi binom.cdf(k, n, p) digunakan untuk menghitung probabilitas mendapatkan k atau lebih sedikit keberhasilan. Ini juga digunakan untuk menghitung probabilitas lebih dari sejumlah keberhasilan tertentu dengan menggunakan komplementaritas (1−CDF).

- Nilai Harapan Distribusi Binomial: Nilai harapan atau rata-rata jumlah keberhasilan dari distribusi binomial dihitung dengan rumus sederhana E[X]=n⋅p. Notebook ini menunjukkannya dengan menghitung ekspektasi jumlah penjualan yang dimenangkan untuk berbagai tingkat keberhasilan.