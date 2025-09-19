Ringkasan Teknis (Apa yang Dipelajari)
Secara keseluruhan, file-file notebook ini mengajarkan tentang kustomisasi dan penyempurnaan visualisasi data menggunakan library Seaborn di Python. Tujuannya adalah untuk mengubah plot standar menjadi grafik yang lebih informatif, menarik secara visual, dan mudah dibaca sesuai dengan kebutuhan audiens.


Materi di dalamnya mencakup tiga area utama:

Mengubah Estetika dan Gaya Plot (File 1: 1Changing plot style.ipynb):

sns.set_style(): Mengubah tampilan latar belakang dan grid pada plot (contoh: "whitegrid", "darkgrid").

sns.set_palette(): Mengatur skema warna yang digunakan pada elemen data (seperti batang atau titik). Ini bisa menggunakan palet bawaan Seaborn (contoh: "Purples", "RdBu") atau palet warna kustom (contoh: ["#39A7D0", "#36ADA4"]).

sns.set_context(): Menyesuaikan skala elemen plot (teks, garis, titik) agar cocok untuk berbagai media, seperti dokumen ("paper"), presentasi ("talk"), atau poster ("poster"), di mana ukuran elemen harus lebih besar.



Memberi Judul dan Label (File 2 & 3: Adding titles and labels):

Membedakan Objek Plot: Seaborn memiliki dua jenis objek plot: Figure-level (FacetGrid) yang dibuat oleh fungsi seperti sns.relplot() atau sns.catplot(), dan Axes-level (AxesSubplot) yang dibuat oleh fungsi seperti sns.lineplot() atau sns.boxplot().

Menambahkan Judul:

Untuk FacetGrid, judul utama ditambahkan menggunakan g.fig.suptitle().

Untuk AxesSubplot, judul ditambahkan menggunakan g.set_title().

Menambahkan Label Sumbu: Label sumbu-x dan sumbu-y diatur menggunakan g.set(xlabel="...", ylabel="...").

Kustomisasi Tambahan: Menggunakan Matplotlib (plt) untuk detail yang lebih spesifik, seperti memutar label di sumbu-x agar tidak tumpang tindih dengan plt.xticks(rotation=90).




Membuat Plot Komparatif yang Kompleks (File 4: 4Putting it all together.ipynb):

hue: Digunakan untuk membagi data menjadi sub-kelompok dalam satu plot yang sama, yang dibedakan oleh warna. Sangat berguna untuk perbandingan langsung.

col (atau row): Digunakan untuk membuat subplot (grafik terpisah) berdasarkan kategori dari sebuah kolom. Ini berguna untuk membandingkan distribusi atau tren di antara segmen data yang berbeda secara berdampingan.

Integrasi: Menggabungkan semua teknik di atas (gaya, palet, judul, label, hue, dan col) untuk menghasilkan visualisasi data yang kaya informasi dan mudah dipahami.





Implementasi di Kehidupan Nyata (Contoh Sederhana)
Bayangkan Anda adalah seorang Manajer Pemasaran di sebuah perusahaan e-commerce dan Anda sedang menganalisis data penjualan.

Membuat Laporan yang Profesional (Terkait File 1):
Saat Anda ingin membuat laporan penjualan untuk rapat internal, Anda ingin grafik Anda terlihat profesional dan sesuai dengan identitas perusahaan. Anda akan menggunakan set_palette() untuk mengubah warna grafik agar cocok dengan warna merek perusahaan Anda. Anda juga akan menggunakan set_context("talk") agar tulisan dan elemen di grafik cukup besar untuk dilihat saat presentasi di layar proyektor.

Menyajikan Data Tanpa Ambiguitas (Terkait File 2 & 3):
Anda membuat grafik yang menunjukkan tren penjualan produk selama setahun. Tanpa judul dan label yang jelas, orang tidak akan mengerti apa yang mereka lihat.

Anda akan menggunakan g.set_title("Pertumbuhan Penjualan Tahunan 2024") untuk memberi judul pada grafik.

Anda akan memberi label pada sumbu-x dan y menggunakan g.set(xlabel="Bulan", ylabel="Total Penjualan (dalam Juta Rupiah)"). Ini memastikan semua orang memahami skala dan unit yang digunakan.

Menemukan Wawasan Tersembunyi untuk Keputusan Bisnis (Terkait File 4):
Manajemen ingin tahu kategori produk mana yang paling populer di kalangan pria dan wanita untuk merancang kampanye iklan yang lebih tertarget.

Anda membuat sebuah box plot yang menunjukkan distribusi usia pembeli. Anda menggunakan hue="Gender" untuk membandingkan distribusi usia antara pria dan wanita dalam satu grafik yang sama.

Selanjutnya, Anda ingin melihat perbandingan minat pada kategori "Elektronik" vs "Fashion" di berbagai kota. Anda membuat bar plot dengan col="Kota" untuk menampilkan grafik penjualan terpisah untuk Jakarta, Surabaya, dan Bandung. Dari sini, Anda mungkin menemukan bahwa produk elektronik sangat laku di Jakarta, sementara produk fashion lebih diminati di Bandung.

Dengan menggunakan teknik-teknik ini, Anda tidak hanya menyajikan data mentah, tetapi Anda menceritakan sebuah kisah yang jelas dari data tersebut, yang pada akhirnya membantu perusahaan mengambil keputusan yang lebih baik.