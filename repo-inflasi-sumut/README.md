# Klasifikasi Inflasi Bulanan Kabupaten/Kota di Sumatera Utara

Tugas Proyek Kelompok, Machine Learning Fundamental (Modul 9).

## Anggota Kelompok

| Nama | NIM |
|---|---|
| M. Affan Apyga | 24141141 |
| Zulfikri Harahap | 24141123 |
| Deryal Rasky | 24141121 |

## Tujuan

Memprediksi apakah inflasi bulanan suatu kabupaten/kota di Provinsi Sumatera Utara bernilai positif, dengan membandingkan KNN, Naive Bayes, Decision Tree, dan SVM menggunakan 5-fold cross-validation.

## Sumber Data

Perkembangan Inflasi 8 Kabupaten/Kota IHK di Provinsi Sumatera Utara (2022=100), Badan Pusat Statistik (BPS) Provinsi Sumatera Utara.
- Tautan: https://sumut.bps.go.id
- Tanggal akses: [isi]
- Berkas di folder `data/`: tahun 2024, 2025, dan 2026 (Januari sampai September).

## Struktur Repo

```
data/          Tiga berkas CSV dari BPS
notebooks/     Notebook klasifikasi (versi lengkap dengan baseline dan pembahasan)
figures/       Confusion matrix dan grafik deret waktu
report/        Laporan IEEE (LaTeX dan PDF)
```

## Cara Menjalankan

1. Buka `notebooks/klasifikasi_inflasi_sumut_lengkap.ipynb` di Google Colab (File, Upload notebook).
2. Upload ketiga file CSV dari folder `data/` ke panel file Colab, dengan nama file yang sama.
3. Pilih Runtime, lalu Run all.

Untuk menjalankan di komputer sendiri, pasang pandas, numpy, matplotlib, dan scikit-learn, lalu jalankan notebook dari folder yang berisi file CSV.

## Ringkasan Hasil

Data: 256 observasi setelah pembuatan fitur inflasi bulan sebelumnya (163 positif, 93 tidak positif). Evaluasi dengan 5-fold stratified cross-validation.

| Model | Akurasi | F1-macro |
|---|---|---|
| Decision Tree (depth=4) | 0,660 ± 0,027 | 0,550 ± 0,069 |
| KNN (k=5) | 0,605 ± 0,035 | 0,490 ± 0,039 |
| Naive Bayes (Gaussian) | 0,558 ± 0,072 | 0,490 ± 0,062 |
| SVM (RBF) | 0,645 ± 0,013 | 0,437 ± 0,026 |
| Baseline (kelas mayoritas) | 0,637 | 0,389 |

Decision Tree memiliki F1-macro tertinggi, tetapi akurasinya hanya sedikit di atas baseline. Lihat laporan untuk pembahasan lengkap dan keterbatasan.
