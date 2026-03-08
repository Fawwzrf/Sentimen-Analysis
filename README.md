# Laporan Proyek Analisis Sentimen Mahasiswa

### Identitas
**Nama/NIM:** NIM H1D023097  
**Institusi:** Informatika Universitas Jenderal Soedirman (Unsoed)

---

### Dokumentasi Proyek

#### 1. Metodologi
Proyek ini mengikuti alur kerja pemrosesan data dan pembelajaran mesin sebagai berikut:
*   **Pengambilan Data:** Mengunduh dataset *Student Feedback* dari Kaggle menggunakan API `opendatasets`.
*   **Eksplorasi & Preprocessing:** Memuat data dari file Excel, melakukan restrukturisasi data (pivot/melt) agar kolom teks dan kategori selaras, serta membersihkan teks dari karakter khusus.
*   **Analisis Sentimen:** Mengklasifikasikan umpan balik menjadi POSITIVE atau NEGATIVE menggunakan model Transformer.
*   **Klasifikasi Zero-Shot:** Memetakan keluhan mahasiswa ke dalam sub-kategori audit spesifik (seperti Punctuality, Material Quality, dll.) tanpa pelatihan ulang model.
*   **Visualisasi:** Menggunakan Seaborn dan Matplotlib untuk menyajikan distribusi sentimen dan pemetaan masalah dalam bentuk heatmap.

#### 2. Dataset
*   **Sumber:** [Student Feedback Dataset (Kaggle)](https://www.kaggle.com/datasets/brarajit18/student-feedback-dataset).
*   **Struktur:** Dataset berisi feedback tekstual mengenai pengajaran (*teaching*), konten kursus (*course content*), pemeriksaan (*examination*), kerja lab (*lab work*), fasilitas perpustakaan (*library*), dan kegiatan ekstrakurikuler.

#### 3. Alasan Teknis Pemilihan Model
Model **DistilBERT** (khususnya `distilbert-base-uncased-finetuned-sst-2-english`) dipilih karena:
*   **Efisiensi Sumber Daya:** DistilBERT 40% lebih kecil dan 60% lebih cepat daripada model BERT standar, namun tetap mempertahankan sekitar 97% kinerjanya.
*   **Kesesuaian Perangkat:** Sangat cocok dijalankan pada environment terbatas tanpa memerlukan waktu inferensi yang lama.
*   **Akurasi:** Memberikan keseimbangan yang optimal antara kecepatan pemrosesan teks dan akurasi klasifikasi sentimen.
