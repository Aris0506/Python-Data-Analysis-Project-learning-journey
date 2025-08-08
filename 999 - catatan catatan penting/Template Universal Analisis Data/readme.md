Berikut adalah Template Universal Analisis Data yang mencakup pertanyaan-pertanyaan paling umum yang hampir selalu ditanyakan pada setiap dataset. 
Simpan ini sebagai "peta" Anda.

### Fase 1: Perkenalan & Pemeriksaan Kesehatan Data (EDA Awal)
Tujuan: Memahami data Anda secara umum sebelum melakukan analisis mendalam.

Pertanyaan 1: "Seperti apa data ini?"

Kode: df.head()

Untuk melihat 5 baris pertama dan mendapatkan gambaran.

Pertanyaan 2: "Seberapa besar datanya dan apa saja isi kolomnya?"

Kode: df.info()

Untuk melihat jumlah baris, nama kolom, tipe data, dan jumlah data kosong.

Pertanyaan 3: "Apakah ada data yang hilang?"

Kode: df.isnull().sum()

Untuk menghitung jumlah sel kosong di setiap kolom.

Pertanyaan 4: "Bagaimana ringkasan statistik untuk kolom angka?"

Kode: df.describe()

Untuk melihat rata-rata, standar deviasi, nilai minimum, maksimum, dll. dari semua kolom numerik.

### Fase 2: Analisis Satu Variabel (Univariat)
Tujuan: Memahami setiap kolom secara individual.

Pertanyaan 5 (Untuk Kolom Kategori/Teks): "Distribusi kategorinya seperti apa? Mana yang paling umum?"

Kode: df['nama_kolom_kategori'].value_counts()

Visualisasi: sns.countplot(y='nama_kolom_kategori', data=df)

Pertanyaan 6 (Untuk Kolom Angka): "Bagaimana sebaran datanya? Apakah ada nilai aneh (outlier)?"

Visualisasi (Sebaran): sns.histplot(data=df, x='nama_kolom_angka', kde=True)

Visualisasi (Outlier): sns.boxplot(data=df, x='nama_kolom_angka')

### Fase 3: Analisis Hubungan Dua Variabel (Bivariat)
Tujuan: Menemukan hubungan atau perbandingan antara dua kolom.

Pertanyaan 7 (Angka vs Kategori): "Apakah rata-rata nilai [angka] berbeda untuk setiap [kategori]?"

Contoh: Apakah rata-rata popularitas berbeda untuk setiap genre?

Visualisasi: sns.barplot(data=df, x='nama_kolom_kategori', y='nama_kolom_angka')

Pertanyaan 8 (Angka vs Angka): "Apakah ada hubungan/korelasi antara [angka 1] dan [angka 2]?"

Contoh: Apakah lagu yang lebih panjang cenderung lebih populer?

Visualisasi: sns.scatterplot(data=df, x='nama_kolom_angka_1', y='nama_kolom_angka_2')

Kode Korelasi: df[['nama_kolom_angka_1', 'nama_kolom_angka_2']].corr()

Pertanyaan 9 (Kategori vs Kategori): "Bagaimana frekuensi kombinasi antara [kategori 1] dan [kategori 2]?"

Contoh: Genre musik apa yang paling sering punya lagu eksplisit?

Kode: pd.crosstab(df['nama_kolom_kategori_1'], df['nama_kolom_kategori_2'])

Visualisasi: sns.heatmap(pd.crosstab(df['kategori_1'], df['kategori_2']))

### Fase 4: Analisis Kelompok (Agregasi)
Tujuan: Menghitung statistik untuk kelompok-kelompok data tertentu.

Pertanyaan 10: "Berapa rata-rata/total/jumlah [kolom angka] untuk setiap [kolom kategori]?"

Ini adalah Misi 9 kita: Berapa rata-rata popularitas untuk setiap genre?

Kode: df.groupby('nama_kolom_kategori')['nama_kolom_angka'].mean() (Bisa juga .sum(), .count(), .max(), dll.)

Ingat: Selalu .reset_index() setelah groupby jika ingin di-plotting.
