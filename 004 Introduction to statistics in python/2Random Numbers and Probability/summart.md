Catatan: Angka Acak dan Probabilitas dalam Python

Dokumen ini merangkum konsep-konsep penting dari modul pengenalan statistik menggunakan Python, dengan fokus pada probabilitas, sampling, dan berbagai distribusi probabilitas.


1. Konsep Dasar Probabilitas dan Sampling

Probabilitas adalah ukuran kemungkinan suatu peristiwa terjadi, dengan nilai antara 0 (tidak mungkin) sampai 1 (pasti terjadi).

Rumus Dasar Probabilitas:

𝑃(event)=Jumlah cara peristiwa bisa terjadi
         Total jumlah kemungkinan hasil

Contoh: Peluang mendapatkan 'kepala' saat melempar koin adalah 1/2 atau 50


Sampling

Sampling Tanpa Penggantian (Without Replacement):
Setiap item yang dipilih tidak dikembalikan ke populasi. Pilihan berikutnya bergantung pada hasil sebelumnya (dependent).
Contoh: Jika Brian sudah terpilih dari 4 orang, peluang Claire terpilih berikutnya adalah 1/3


Sampling Dengan Penggantian (With Replacement):
Setiap item yang dipilih dikembalikan, sehingga setiap pilihan bersifat independen (independent).
Contoh: Peluang Claire terpilih tetap 1/4 setiap saat, tidak peduli siapa yang terpilih sebelumnya.

Reproducibility dalam Kode
Menggunakan np.random.seed() untuk memastikan hasil acak yang dihasilkan bisa direproduksi (sama setiap kali dijalankan).



2. Distribusi Diskrit

Distribusi probabilitas untuk hasil yang terpisah dan dapat dihitung (diskrit).

Distribusi Seragam Diskrit (Discrete Uniform Distribution)

Setiap hasil memiliki probabilitas yang sama.
Contoh: Lemparan dadu adil, setiap sisi (1–6) memiliki probabilitas  1/6
Expected Value (Nilai Harapan)

Hukum Bilangan Besar (Law of Large Numbers)
Semakin besar ukuran sampel, rata-rata sampel semakin mendekati nilai harapan teoretis populasi.



3. Distribusi Kontinu

Distribusi probabilitas untuk hasil yang dapat mengambil nilai apa pun dalam rentang tertentu (kontinu).

Distribusi Seragam Kontinu (Continuous Uniform Distribution)

Setiap hasil dalam rentang memiliki probabilitas yang sama. Probabilitas dihitung sebagai luas area di bawah kurva distribusi probabilitas.

Di Python, fungsi uniform.cdf(x, min, range) digunakan untuk menghitung probabilitas kumulatif 
P(hasil≤x)

4. Distribusi Binomial

Distribusi probabilitas diskrit yang menggambarkan jumlah keberhasilan dari serangkaian uji coba independent dengan dua kemungkinan hasil (sukses/gagal).

Karakteristik:

n: jumlah total uji coba

p: probabilitas keberhasilan dalam satu uji coba

Expected Value: E(X)=n×p

Contoh: Nilai harapan jumlah 'kepala' dari 10 lemparan koin adalah 10×0.5=5

Fungsi di Python (scipy.stats.binom):

binom.rvs(n, p, size): menghasilkan sampel acak dari distribusi binomial.
binom.pmf(k, n, p): menghitung probabilitas massa P(X=k) peluang tepat k keberhasilan.
binom.cdf(k, n, p): menghitung probabilitas kumulatif P(X≤k)  peluang paling banyak k keberhasilan.
