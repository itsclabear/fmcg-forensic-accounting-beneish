# fmcg-forensic-accounting-beneish
Forensic accounting and earnings quality analysis for Indonesia FMCG sector using Beneish M-Score (2022–2024)
# FMCG Earnings Quality Analysis: Beneish M-Score (2022–2024)

Proyek ini bertujuan untuk mengecek kualitas laba (*earnings quality*) sekaligus menyaring risiko manipulasi laporan keuangan pada 4 emiten FMCG besar di Bursa Efek Indonesia (BEI):
* **UNVR** (PT Unilever Indonesia Tbk)
* **ICBP** (PT Indofood CBP Sukses Makmur Tbk)
* **MYOR** (PT Mayora Indah Tbk)
* **INDF** (PT Indofood Sukses Makmur Tbk)

Pengecekan ini dilakukan sebagai tahap awal sebelum masuk ke pemodelan valuasi (seperti DCF atau Relative Valuation), untuk memastikan angka laba bersih yang dilaporkan memang valid dan didukung oleh arus kas riil.

---

## Metodologi

Analisis menggunakan model **Beneish M-Score (8 Variabel)**:

$$\text{M-Score} = -4.84 + 0.920 \times \text{DSRI} + 0.528 \times \text{GMI} + 0.404 \times \text{AQI} + 0.892 \times \text{SGI} + 0.115 \times \text{DEPI} - 0.172 \times \text{SGAI} + 4.679 \times \text{TATA} - 0.327 \times \text{LVGI}$$

**Acuan Batas (Threshold):**
* **M-Score > -1.78:** Terindikasi Ada Manipulasi (*Likely Manipulator*)
* **M-Score ≤ -1.78:** Bebas Indikasi Manipulasi (*Non-Manipulator*)

---

## Tools yang Digunakan

* **Google Sheets / Excel:** Ekstraksi data dari laporan keuangan auditan (2022–2024), pembentukan rumus M-Score dinamis, dan kalkulasi rasio.
* **Python (Pandas, Matplotlib):** Pemrosesan data mentah dan pembuatan visualisasi perbandingan M-Score antar-emiten.

---

## Temuan Utama

1. **Seluruh Emiten Aman (Non-Manipulator):** Semua perusahaan sampel memiliki nilai M-Score jauh di bawah *threshold* -1.78 untuk periode 2022 hingga 2024:
   * **UNVR (2024):** -2.65
   * **INDF (2024):** -2.58
   * **MYOR (2024):** -2.52
   * **ICBP (2024):** -2.48
2. **Kualitas Laba Terjaga:** Nilai **TATA (Total Accruals to Total Assets)** berada di angka negatif yang konsisten. Ini menunjukkan bahwa laba bersih didukung penuh oleh arus kas dari aktivitas operasi (CFO), bukan sekadar rekayasa akrual.
3. **Pengakuan Pendapatan Wajar:** Rasio **DSRI (Days Sales in Receivables Index)** berada di kisaran normal (0.98–1.02), menandakan tidak ada penumpukan piutang tak tertagih yang sengaja ditahan untuk mendongkrak omzet.

**Kesimpulan:** Laporan keuangan keempat perusahaan ini kredibel dan transparan untuk dijadikan dasar analisis rasio lanjutan maupun proyeksi valuasi saham.
