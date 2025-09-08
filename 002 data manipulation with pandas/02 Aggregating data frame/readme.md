ini adalah pembelajaran tentang aggregating dataframe khususnya membahas

- statistik umum
    • mean(): Menghitung nilai rata-rata. 
    • .median(): Menemukan nilai tengah. 
    • .min(): Menemukan nilai terkecil. 
    • .max(): Menemukan nilai terbesar. 
    • .sum(): Menjumlahkan semua nilai. 
    • .std(): Menghitung standar deviasi (ukuran sebaran data).

- menghitung nilai
    • Menghindari Perhitungan Ganda .drop_duplicates()
    • Menghitung Nilai dengan .value_counts()

- Meringkas Data: Statistik Berkelompok
    • Metode .groupby()

- Meringkas Data: Pivot Tables
  Metode .pivot_table() memiliki beberapa argumen utama: 
    • values: Kolom yang ingin Anda ringkas (dihitung statistiknya). 
    • index: Kolom yang akan menjadi baris dari pivot table Anda. 
    • columns: Kolom yang akan menjadi kolom dari pivot table Anda. 
    • aggfunc: Fungsi agregasi yang ingin Anda gunakan (default-nya adalah 'mean'). 
    • fill_value: Nilai untuk mengisi sel yang kosong (jika ada kombinasi baris/kolom 
       yang tidak memiliki data). 
    • margins=True: Menambahkan baris dan kolom "All" yang berisi total ringkasan.
