file ini membahas materi pembelajaran introduction to statistics in python dengan sub bab random number and probability in python:
1. Probabilitas = = peluang suatu peristiwa terjadi
   
2. Sampling (Pengambilan Sampel)
- Sampling tanpa replacement → peluang berubah setelah satu item diambil.
- Sampling dengan replacement → peluang tetap sama, tiap pengambilan independen.
- np.random.seed() → memastikan hasil random bisa direplikasi.

3. Independent vs Dependent Events
- Independent → hasil percobaan pertama tidak memengaruhi percobaan berikutnya.
- Dependent → hasil percobaan pertama memengaruhi peluang berikutnya.

4. Distribusi Diskrit
- Distribusi probabilitas: memetakan semua kemungkinan hasil dan peluangnya.
- Expected value = rata-rata teoretis.
- Law of Large Numbers → makin besar ukuran sampel, rata-rata sampel mendekati nilai harapan (expected value).

5. Distribusi Kontinu
- Distribusi uniform kontinu → semua nilai dalam rentang tertentu sama peluangnya.
- Probabilitas dihitung sebagai luas area di bawah kurva.
- scipy.stats.uniform → digunakan untuk menghitung CDF, peluang lebih besar/kecil, dan generate angka acak.

  6. . Distribusi Binomial
- Binomial → jumlah keberhasilan dalam sejumlah percobaan independen.
- Parameter:
    n = jumlah percobaan
    p = peluang sukses
- fungsi penting:
    - binom.pmf(k, n, p) → peluang tepat k sukses
    - binom.cdf(k, n, p) → peluang ≤ k sukses
- Expected value =  n×p

Materi ini mengajarkan dasar statistik dengan Python: mulai dari probabilitas, sampling, konsep independensi, 
distribusi diskrit & kontinu, hingga distribusi binomial. Praktiknya menggunakan numpy, pandas, dan scipy.stats.
