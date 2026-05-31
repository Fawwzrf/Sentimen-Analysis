# Analisis Sentimen Mahasiswa

Proyek Analisis Sentimen Mahasiswa adalah sistem pemrosesan bahasa alami (NLP) untuk mengklasifikasikan dan memetakan umpan balik mahasiswa secara otomatis ke dalam kategori spesifik. Proyek ini dibangun menggunakan Python, Pandas, dan model DistilBERT dari library Transformers Hugging Face.

---

### Metodologi
Proyek ini ngikutin alur kerja Machine Learning dan Data Science yang simpel tapi efektif:
* **Tarik Data:** Kita download dataset *Student Feedback* langsung dari Kaggle pakai API `opendatasets`.
* **Bersih-bersih Data (Preprocessing):** Load data dari file Excel, terus di-restrukturisasi (pakai trik pivot/melt) biar kolom teks sama kategorinya pas selaras. Nggak lupa teksnya juga dibersihin dari karakter-karakter yang aneh.
* **Cek Sentimen:** Di sini kita pakai model Transformer buat nge-klasifikasiin feedback mahasiswa, apakah itu masuknya *POSITIVE* atau *NEGATIVE*.
* **Zero-Shot Classification:** Ini bagian kerennya! Keluhan mahasiswa langsung dipetakan ke sub-kategori spesifik (misal: *Punctuality*, *Material Quality*, dll.) tanpa perlu repot ngelatih ulang model dari nol.
* **Visualisasi Kece:** Biar gampang dibaca, hasilnya disajikan jadi grafik distribusi dan pemetaan *heatmap* masalah yang interaktif pakai Seaborn dan Matplotlib.

### Tentang Dataset
* **Sumber:** Datanya diambil dari [Student Feedback Dataset di Kaggle](https://www.kaggle.com/datasets/brarajit18/student-feedback-dataset).
* **Isinya Apa Aja?** Dataset ini penuh dengan feedback teks dari mahasiswa soal pengajaran (*teaching*), materi kuliah (*course content*), ujian (*examination*), praktikum lab (*lab work*), fasilitas perpus (*library*), sampai kegiatan ekstrakurikuler.

### Kenapa Pilih DistilBERT?
Model **DistilBERT** (spesifiknya versi `distilbert-base-uncased-finetuned-sst-2-english`) dipilih bukan tanpa alasan:
* **Hemat Resource:** Ukurannya 40% lebih kecil dan 60% lebih ngebut dari model BERT standar, tapi tetep bisa pertahanin sekitar 97% kinerjanya.
* **Ramah Device:** Enak banget buat dijalanin di *environment* yang terbatas karena nggak butuh waktu inferensi yang lama.
* **Akurat:** Ngasih *sweet spot* alias keseimbangan yang pas banget antara kecepatan pemrosesan teks dan keakuratan saat klasifikasi sentimen.
