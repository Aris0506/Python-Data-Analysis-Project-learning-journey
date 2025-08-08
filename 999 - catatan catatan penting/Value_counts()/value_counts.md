
#### Hari ini saya belajar fungsi .value_counts() yang gunanya untuk menghitung isi data di dalam kolom, lalu mengurutkannya dari yang paling banyak. Jika kita ingin mengambil salah satu nama kategorinya, kita gunakan .index diikuti dengan nomor posisinya, seperti .index[0] untuk mengambil yang teratas.

contoh Kode :
##### Misi: Mencari negara asal pemenang Nobel yang paling umum.
##### Dataset kita bernama 'nobel'

##### 1. Hitung & urutkan semua negara di kolom 'birth_country'.
##### 2. Ambil daftar nama negaranya (.index).
##### 3. Ambil nama di posisi pertama ([0]).

top_country = nobel['birth_country'].value_counts().index[0]

##### Tampilkan hasilnya
print("Negara pemenang teratas adalah:", top_country)
