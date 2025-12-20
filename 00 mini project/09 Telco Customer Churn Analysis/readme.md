
Topik: Business to Data Thinking (Week 1)
Tanggal: 19 Desember 2025
Status: Misi Selesai ✅

📂  DOKUMENTASI PROYEK (Studi Kasus)
Judul Dataset: Telco Customer Churn Tipe Masalah: Duit Bocor (Cost/Risk Reduction) 🔴

A. Business Understanding (4 Baris Sakti)
1. Masalah: Perusahaan kehilangan pendapatan rutin (recurring revenue) karena pelanggan berhenti berlangganan.

2. Entitas: Pelanggan perorangan (1 baris data = 1 Orang).

3. Target (Akibat): Kolom Churn (Yes/No).

4. Variabel (Sebab):
    - Komitmen: Jenis Kontrak (Bulanan vs Tahunan).
    - inansial: Tagihan Bulanan (Monthly Charges).

B. Hasil Diagnosa (Data Insight)
Setelah melakukan EDA (Visualisasi), ditemukan 2 pola utama:

1. Masalah Komitmen: Pelanggan dengan Kontrak Bulanan (Month-to-month) memiliki tingkat Churn yang jauh lebih tinggi dibanding pelanggan kontrak tahunan. Mereka adalah kelompok paling tidak setia.

2. Masalah Harga: Pelanggan yang Churn memiliki rata-rata Tagihan Bulanan yang Lebih Tinggi. Ini mengindikasikan mereka sensitif terhadap harga atau merasa nilai (value) yang didapat tidak sebanding dengan biaya.

C. Rekomendasi Bisnis (Action Plan)
1. Strategi Kunci (Lock-in): Buat promo khusus (misal: Diskon 20%) bagi pelanggan bulanan yang bersedia pindah ke kontrak 1 tahun. Tujuannya untuk meningkatkan komitmen mereka.

2. Retensi Premium: Identifikasi pelanggan dengan tagihan tinggi namun berisiko kabur, lalu tawarkan benefit tambahan (misal: speed upgrade gratis) agar mereka merasa biaya yang dikeluarkan sepadan (worth it).