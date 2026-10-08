# Prediksi Keterlambatan Pembayaran Invoice

## Deskripsi

Proyek ini merupakan studi kasus sederhana penerapan **Machine Learning untuk memprediksi keterlambatan pembayaran invoice**.

Proyek ini dibuat berdasarkan materi seminar **“Make Sense of Data with Analysis and AI”** yang membahas pentingnya data preparation, pemilihan model, class imbalance, evaluasi model, serta penggunaan AI sebagai alat bantu pengambilan keputusan.

Model yang digunakan adalah **Logistic Regression**, dengan perbandingan antara model biasa dan model yang menggunakan **class weighting** untuk menangani ketidakseimbangan kelas.

## Tujuan

Tujuan proyek ini adalah:

- Memprediksi apakah suatu invoice akan mengalami keterlambatan pembayaran.
- Mengetahui pengaruh **class imbalance** terhadap performa model.
- Membandingkan Logistic Regression biasa dengan Logistic Regression menggunakan `class_weight="balanced"`.
- Mengevaluasi model menggunakan metrik yang sesuai, terutama **Recall**.
- Menghasilkan insight yang dapat digunakan sebagai pendukung pengambilan keputusan.

## Studi Kasus

Sebuah perusahaan memiliki data transaksi invoice dari pelanggan. Tidak semua invoice dibayar tepat waktu sehingga perusahaan ingin mengetahui invoice mana yang memiliki kemungkinan terlambat.

Prediksi ini dapat digunakan sebagai **decision support**, misalnya untuk membantu perusahaan menentukan invoice yang perlu mendapatkan perhatian atau tindak lanjut lebih awal.

## Dataset

Dataset yang digunakan merupakan **dataset sintetis** yang dibuat menggunakan Python.

Dataset berisi sekitar 1.000 data invoice dengan beberapa atribut, antara lain:

- `invoice_amount` — jumlah nilai invoice
- `customer_age` — usia pelanggan
- `customer_category` — kategori pelanggan
- `payment_term` — jangka waktu pembayaran
- `previous_late_count` — jumlah keterlambatan sebelumnya
- `previous_invoice_count` — jumlah invoice sebelumnya
- `average_payment_delay` — rata-rata keterlambatan pembayaran
- `customer_tenure` — lama menjadi pelanggan
- `discount` — persentase diskon
- `late` — target, yaitu apakah invoice terlambat atau tidak

Target `late` memiliki kondisi **class imbalance**, sehingga jumlah invoice yang terlambat lebih sedikit dibandingkan invoice yang tidak terlambat.

## Metode

Tahapan utama yang dilakukan:

1. Data Understanding
2. Pemeriksaan data dan distribusi target
3. Preprocessing data
4. Pembagian data training dan testing
5. Logistic Regression
6. Logistic Regression dengan `class_weight="balanced"`
7. Evaluasi dan perbandingan model

### Model

Model utama yang digunakan:

**Logistic Regression**

Dua konfigurasi dibandingkan:

- Logistic Regression standar
- Logistic Regression dengan `class_weight="balanced"`

Penggunaan `class_weight="balanced"` bertujuan memberikan bobot lebih besar kepada kelas yang jumlah datanya lebih sedikit.

## Evaluasi

Performa model dievaluasi menggunakan:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

Dalam kasus ini, **Recall menjadi metrik penting** karena perusahaan ingin sebanyak mungkin mendeteksi invoice yang berpotensi terlambat.

Accuracy yang tinggi belum tentu menunjukkan model yang baik apabila terdapat **class imbalance**.

## Teknologi

- Python
- Google Colab
- Jupyter Notebook (`.ipynb`)
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

## Cara Menjalankan

Proyek dapat dijalankan menggunakan **Google Colab**.

1. Buka file `invoice_prediction.ipynb` menggunakan Google Colab.
2. Jalankan notebook dari awal hingga akhir.
3. Dataset sintetis akan dibuat dan digunakan untuk proses analisis serta pemodelan.
4. Hasil preprocessing, training, evaluasi, dan perbandingan model dapat dilihat langsung pada notebook.

## Struktur Repository

```text
invoice-payment-prediction/
├── invoice_prediction.ipynb
├── invoices.csv
├── README.md
└── requirement.txt
```

### Keterangan

- `invoice_prediction.ipynb` — notebook utama yang berisi seluruh proses analisis dan machine learning.
- `invoices.csv` — dataset invoice sintetis yang digunakan dalam proyek.
- `README.md` — dokumentasi proyek.

## Kesimpulan

Proyek ini menunjukkan bahwa dalam kasus prediksi keterlambatan pembayaran invoice, **pemilihan metrik evaluasi harus disesuaikan dengan tujuan bisnis**.

Pada kondisi class imbalance, accuracy saja tidak cukup untuk menilai performa model. Recall, precision, F1-score, dan confusion matrix perlu diperhatikan untuk mengetahui kemampuan model dalam mendeteksi invoice yang terlambat.

Hasil prediksi model digunakan sebagai **pendukung keputusan**, bukan sebagai pengganti keputusan manusia.

## Referensi

Arisal, A. (2026). *Make Sense of Data with Analysis and AI*. Research Center for Data and Information Sciences, Badan Riset dan Inovasi Nasional (BRIN).
