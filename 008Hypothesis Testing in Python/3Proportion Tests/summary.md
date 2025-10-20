📘 **RINGKASAN BAB: UJI PROPORSI & CHI-SQUARE**

---

### 🧮 1. **Uji Proporsi 1 Sampel**

**Tujuan:** Menguji apakah proporsi populasi sama dengan nilai tertentu.
**Contoh:** Apakah benar 40% pengguna aplikasi berusia *di bawah 25 tahun*?

**Langkah-langkah:**

1. Rumuskan hipotesis:

   * H₀: p = p₀
   * H₁: p ≠ p₀
2. Hitung proporsi sampel:
   p̂ = (jumlah kategori yang diuji) / n
3. Hitung z-score:
   z = (p̂ − p₀) / √[p₀(1 − p₀)/n]
4. Hitung p-value dari z.
5. Bandingkan dengan α (misal 0.05).

**Keputusan:**

* Jika p < α → **Tolak H₀** (ada perbedaan signifikan).
* Jika p > α → **Gagal menolak H₀** (tidak ada bukti kuat perbedaan).

---

### ⚖️ 2. **Uji Proporsi 2 Sampel**

**Tujuan:** Membandingkan dua proporsi dari dua kelompok.
**Contoh:** Apakah proporsi pembeli *di bawah 25 tahun* sama dengan *di atas 25 tahun*?

**Langkah-langkah:**

1. H₀: p₁ = p₂
   H₁: p₁ ≠ p₂
2. Hitung p̂₁ dan p̂₂ dari masing-masing kelompok.
3. Hitung pooled proportion:
   p̂ = (x₁ + x₂) / (n₁ + n₂)
4. Hitung standard error:
   SE = √[p̂(1 − p̂)(1/n₁ + 1/n₂)]
5. Hitung z-score dan p-value seperti sebelumnya.

**Interpretasi:**

* p < α → Ada perbedaan proporsi antar kelompok.
* p > α → Tidak ada bukti cukup perbedaan proporsi.

---

### 🧩 3. **Uji Chi-Square (Independensi)**

**Tujuan:** Menguji apakah dua variabel kategorikal saling berhubungan.
**Contoh:** Apakah *kategori usia* berhubungan dengan *tingkat kepuasan*?

**Langkah-langkah:**

1. Buat tabel silang (crosstab).
2. Rumuskan hipotesis:

   * H₀: Tidak ada hubungan (independen).
   * H₁: Ada hubungan (dependen).
3. Lakukan uji Chi-Square:
   χ² = Σ (O − E)² / E

   * O = frekuensi observasi
   * E = frekuensi harapan (expected)
4. Hitung p-value dari distribusi χ².

**Keputusan:**

* p < α → Ada hubungan signifikan antar variabel.
* p > α → Gagal menolak H₀ (belum ada cukup bukti adanya hubungan).

---

### 💡 Catatan Penting

* **Z-test / t-test** → untuk **data numerik (mean)**.
* **Chi-Square** → untuk **data kategorikal (frekuensi)**.
* Kalimat aman dalam kesimpulan:

  > “Belum ada cukup bukti yang kuat untuk menolak H₀.”

---
