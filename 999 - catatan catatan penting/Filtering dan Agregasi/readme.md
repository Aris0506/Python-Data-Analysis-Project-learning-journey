### Hari ini saya belajar 2 konsep sekaligus yaitu filtering yang sekaligus mmembuat kolom barunya dan agregasi yang juga sama-sama membuatkan kolom baru sekaligus lalu didalam agregasi kita juga menggunakan fungsi groupby() untuk mengumpulkan/atau mengelompokan kolom decade lalu menghitung rata-rata nya menggunakan fungsi .mean() berdasarkan catatan tersebut berikut penjelasan ringkasnya: 

1. Konsep #1: Filtering Kondisional & Membuat Kolom Baru
- Tujuan: Membuat kolom baru yang isinya adalah label True/False berdasarkan suatu kondisi. Ini adalah langkah awal dari proses filtering, di mana kita tidak memilih baris, tapi mengevaluasi setiap baris.

Contoh Kode:
### Membuat kolom 'usa_born_winner' yang isinya True/False.
### Isinya True jika 'birth_country' adalah 'United States of America', selain itu False.
nobel['usa_born_winner'] = nobel['birth_country'] == 'United States of America'


2. Konsep #2: Agregasi per Kelompok
- Tujuan: Mengelompokkan data berdasarkan suatu kriteria (seperti dekade), lalu menghitung statistik (seperti proporsi/rata-rata) untuk setiap kelompok.

import numpy as np

### --- Langkah A: Membuat kolom grup 'decade' ---
### Mengubah tahun (misal: 1986) menjadi dekade (1980)
nobel['decade'] = (np.floor(nobel['year'] / 10) * 10).astype(int)

### --- Langkah B: Menghitung rata-rata (proporsi) per grup ---
### Mengelompokkan berdasarkan 'decade' dan menghitung proporsi pemenang dari AS
prop_usa_winners = nobel.groupby('decade')['usa_born_winner'].mean()

### Menampilkan hasilnya
print(prop_usa_winners)
