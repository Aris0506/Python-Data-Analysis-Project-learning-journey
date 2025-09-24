# Analisis Eksplorasi Data (EDA) Perilaku Pelanggan Restoran

## 📌 Ringkasan Proyek
Project ini merupakan analisis data eksplorasi (EDA) untuk memahami faktor-faktor yang memengaruhi perilaku pelanggan di sebuah restoran, khususnya terkait pemberian tip. Analisis ini menggunakan dataset **"tips"** yang tersedia di library Seaborn dan berfokus pada visualisasi data untuk menemukan pola dan wawasan.

## 🎯 Tujuan
- Mengidentifikasi hari dan waktu paling ramai.  
- Menganalisis hubungan antara total tagihan dengan besarnya tip yang diberikan.  
- Membandingkan perilaku antara kelompok pelanggan yang berbeda (misalnya, perokok vs. non-perokok, pria vs. wanita).  
- Membuat visualisasi yang informatif dan siap saji untuk presentasi kepada manajemen.  

## 📚 Pustaka yang Digunakan
- **seaborn**: Untuk membuat visualisasi data statistik yang menarik.  
- **matplotlib.pyplot**: Untuk kustomisasi plot dan menampilkannya.  
- **pandas**: Untuk memuat dan mengelola dataset.  

## 🔎 Analisis dan Temuan

### 1. Eksplorasi Awal: Distribusi Pelanggan
**Temuan**: Hari **Sabtu** dan **Minggu** adalah hari dengan jumlah pelanggan tertinggi. Secara keseluruhan, jumlah pelanggan pria lebih banyak daripada pelanggan wanita.

### 2. Hubungan Antar Variabel: Total Tagihan vs. Tip
**Temuan**: Secara umum, semakin tinggi total tagihan, semakin tinggi pula tip yang diberikan. Analisis lebih lanjut menunjukkan bahwa pelanggan **perokok** saat makan malam (**Dinner**) cenderung memberikan tip yang sangat besar, terutama pada tagihan yang tinggi.

### 3. Perbandingan Antar Kategori
- **Distribusi Tagihan**: Hari **Minggu** memiliki median (nilai tengah) tagihan tertinggi, sedangkan Hari **Sabtu** menunjukkan variasi (rentang) tagihan yang paling lebar.  
- **Rata-rata Tip**: Tidak ditemukan perbedaan yang signifikan secara statistik antara rata-rata tip yang diberikan oleh **perokok** dan **non-perokok**. Meskipun ada sedikit kecenderungan perokok memberi tip lebih besar saat makan siang, interval kepercayaannya saling tumpang tindih, yang mengindikasikan perbedaannya kemungkinan besar hanya variasi acak.

### 4. Visualisasi Final: Pengaruh Ukuran Rombongan
**Temuan**: Rata-rata tip yang diberikan cenderung meningkat seiring dengan bertambahnya jumlah orang dalam satu rombongan (**size**), baik pada waktu makan siang maupun makan malam. Rombongan yang lebih besar memberikan tip rata-rata yang lebih tinggi. Visualisasi ini telah dipoles untuk tujuan presentasi.
