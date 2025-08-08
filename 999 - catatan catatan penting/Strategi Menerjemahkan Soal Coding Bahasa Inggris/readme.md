Strategi Menerjemahkan Soal Coding Bahasa Inggris
Setiap soal coding dalam bahasa Inggris adalah seperti resep masakan dalam bahasa asing. 
Kunci untuk menyelesaikannya adalah dengan memisahkan masalah bahasa dari masalah logika coding.

Langkah 1: Terjemahkan Kasar (Gunakan Google Translate)
Salin seluruh soal ke Google Translate untuk mendapatkan gambaran besar dalam Bahasa Indonesia. Jangan khawatir jika tata bahasanya aneh.

Langkah 2: Jadilah Detektif Kata Kunci
Baca kembali soal asli dalam Bahasa Inggris. Fokus hanya pada kata kerja (perintah) dan kata benda (data) yang penting.

Contoh Soal:

"Calculate the mean age for each gender, and then determine which gender has the highest average age."

Hasil Deteksi:

Kata Perintah: Calculate, determine.

Kata Data: mean age, each gender, highest average age.

Langkah 3: Buat Rencana dalam Bahasa Indonesia (Pseudocode)
Tulis ulang hasil deteksi Anda menjadi rencana langkah-demi-langkah yang logis dalam bahasa Anda sendiri.

Rencana:

Aku harus mengelompokkan data berdasarkan gender.

Untuk setiap kelompok, aku harus menghitung rata-rata umur.

Aku harus mencari gender mana yang punya rata-rata umur tertinggi.

Langkah 4: Terjemahkan Rencana ke Kode Pandas
Setelah punya rencana yang jelas, barulah terjemahkan setiap langkah ke dalam kode.

Eksekusi Kode:

"Mengelompokkan" -> .groupby('gender')

"Menghitung rata-rata umur" -> ['age'].mean()

"Mencari yang tertinggi" -> .idxmax() atau .sort_values()

'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

#### 1. Hitung rata-rata (ini sudah sempurna)
high_average = df.groupby('gender')['age'].mean()

#### 2. Langsung cari TAHU SIAPA (indeks) yang punya nilai tertinggi
top_gender = high_average.idxmax()

#### 3. Tampilkan hasilnya
print("Rata-rata umur per gender:")
print(high_average) # Menampilkan tabel rata-rata aslinya

print("\nGender dengan rata-rata umur tertinggi adalah:", top_gender)
