### Template Emas: Alur Kerja Analisis Data dari A sampai Z
Anggap ini adalah Prosedur Standar Operasional (SOP) Anda sebagai seorang detektif data setiap kali memasuki "Tempat Kejadian Perkara" (TKP) baru.

Fase 1: Tiba di TKP (Inspeksi & Perkenalan Data)
Tujuan: Mendapatkan gambaran umum secepat mungkin.

Lihat Situasi: "Seperti apa TKP ini?"

Kode: df.head()

Dapatkan Laporan Awal: "Berapa banyak barang bukti? Apa saja jenisnya?"

Kode: df.info()

Fase 2: Forensik Awal (Validasi & Pembersihan)
Tujuan: Memastikan semua barang bukti valid dan tidak ada yang hilang atau palsu.

Cek Bukti Hilang: "Apakah ada sidik jari atau barang bukti yang hilang?"

Kode: df.isnull().sum()

Cek Bukti Ganda: "Apakah ada barang bukti yang sama persis dilaporkan dua kali?"

Kode: df.duplicated().sum()

Pastikan Label Bukti Benar: "Apakah label untuk 'bukti cair' sudah benar 'cair', bukan 'teks'?"

Kode: df['nama_kolom'].astype('tipe_data_baru')

Fase 3: Interogasi & Analisis Mendalam
Tujuan: Menginterogasi setiap "saksi" (kolom) dan mencari hubungan antar "saksi" untuk menemukan cerita.

A. Interogasi Individual (Analisis Satu Variabel)
Saksi Kategori (Kolom Teks): "Siapa Anda dan seberapa sering Anda muncul?"

Kode: df['kolom_kategori'].value_counts()

Visualisasi: sns.countplot(y='kolom_kategori', data=df)

Saksi Angka (Kolom Numerik): "Bagaimana karakteristik dan sebaran Anda?"

Kode: df['kolom_angka'].describe()

Visualisasi: sns.histplot(x='kolom_angka', data=df) atau sns.boxplot(x='kolom_angka', data=df)

B. Interogasi Gabungan (Analisis Hubungan)
Hubungan Angka & Kategori: "Apakah [Saksi Angka] punya cerita berbeda untuk setiap [Saksi Kategori]?"

Contoh: Apakah popularitas berbeda untuk setiap genre?

Visualisasi: sns.barplot(x='kolom_kategori', y='kolom_angka', data=df)

Hubungan Angka & Angka: "Apakah ada hubungan antara [Saksi Angka 1] dan [Saksi Angka 2]?"

Contoh: Apakah durasi berhubungan dengan popularitas?

Visualisasi: sns.scatterplot(x='kolom_angka_1', y='kolom_angka_2', data=df)

C. Interogasi Kelompok (Analisis Agregasi)
Kesaksian Kelompok: "Jika para saksi dikelompokkan berdasarkan [Kategori], apa kesimpulan rata-rata/total dari [Angka]?"

Contoh: Berapa rata-rata popularitas per genre?

Kode: df.groupby('kolom_kategori')['kolom_angka'].mean().reset_index()

