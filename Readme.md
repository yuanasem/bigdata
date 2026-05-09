# MIMIC-IV ICU Data Wrangling & Reproducibility Pipeline

[cite_start]Proyek ini merupakan implementasi *pipeline* pengolahan data rekam medis elektronik (EHR) skala besar menggunakan dataset **MIMIC-IV ICU Demo**[cite: 355, 450]. [cite_start]Fokus utama proyek ini adalah menerapkan prinsip **Reproduksibilitas** dan **Validitas Klinis** dalam pemrosesan data *high-dimensional* untuk mendukung keputusan medis yang transparan[cite: 321, 322].

## 1. Latar Belakang & Tujuan
[cite_start]Analisis data kesehatan sering kali menghadapi hambatan dalam hal replikasi hasil karena kurangnya dokumentasi pada "diskresi peneliti" dalam *pipeline* data[cite: 326]. Proyek ini bertujuan untuk:
* [cite_start]Membangun *pipeline* pembersihan data yang efisien dan dapat direproduksi[cite: 369, 403].
* Mengimplementasikan standar pembersihan data medis sesuai dengan metodologi **Gupta et al. (2022)[cite_start]**[cite: 462].
* Mematuhi 5 rekomendasi utama untuk reproduksibilitas penelitian medis menurut **Streiber et al. (2025)[cite_start]**[cite: 25, 31].

## 2. Prinsip Reproduksibilitas (Streiber et al., 2025)
Proyek ini mengadopsi rekomendasi berikut:
1.  [cite_start]**Prioritas Reproduksibilitas:** Mengalokasikan waktu untuk menyusun kode yang terstruktur dan terdokumentasi[cite: 25, 63].
2.  [cite_start]**Kode yang Komprehensibel:** Menggunakan penamaan variabel yang intuitif, *headings*, dan komentar yang menjelaskan rasionalisasi setiap langkah[cite: 27, 63, 123].
3.  [cite_start]**Transparansi Keputusan:** Melaporkan setiap langkah pembersihan data (*data cleaning*) dan pemilihan sampel secara detail di dalam kode[cite: 28, 66, 133].
4.  [cite_start]**Aksesibilitas:** Menyediakan *Data Dictionary* dan repositori yang rapi untuk memfasilitasi peninjauan sejawat (*peer review*)[cite: 29, 68, 206].

## 3. Metodologi Data (Gupta et al., 2022)
Pemrosesan data mengikuti standar *extensive pipeline* untuk MIMIC-IV:
* **Outlier Removal:** Menggunakan ambang batas statistik (persentil ke-98) untuk mengeliminasi nilai yang tidak masuk akal secara patofisiologi (misal: error sensor alat)[cite: 399, 511, 513].
* [cite_start]**Vectorized Operations:** Menggunakan fungsi vektorisasi Pandas untuk efisiensi komputasi pada data *time-series*[cite: 401, 517].
* [cite_start]**Clinical Grouping:** Fokus pada fitur tanda vital yang relevan secara klinis untuk prediksi risiko (contoh: *Heart Rate*, itemid: 220045)[cite: 400, 490].

## 4. Setup & Instalasi

### Prasyarat
* Python 3.9+
* Pandas
* NumPy

### Struktur Folder
```text
.
├── archive (1)/           # Dataset mentah (Diabaikan oleh .gitignore)
├── venv/                  # Virtual Environment (Diabaikan oleh .gitignore)
├── .gitignore             # Pengaturan pengabaian file besar & sistem
├── Commit_1_Poor.py       # Skrip awal (Kualitas rendah/Tahap 1)
├── Commit_2_Refactored.py # Skrip hasil refaktor (Kualitas baik/Tahap 2)
└── README.md              # Dokumentasi proyek (Tahap 3)
