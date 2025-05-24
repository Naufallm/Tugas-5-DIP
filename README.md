# Analisis Seleksi Fitur untuk Prediksi Nilai Ujian Siswa

## Deskripsi Proyek
Proyek ini bertujuan untuk mengidentifikasi fitur-fitur yang paling relevan dari dataset perilaku siswa yang memengaruhi `exam_score` (nilai ujian). Seleksi fitur adalah tahap krusial dalam pembangunan model Machine Learning yang efektif, karena membantu meningkatkan akurasi, mengurangi *overfitting*, mempercepat waktu pelatihan, dan meningkatkan interpretasi model. Dalam analisis ini, kami menggunakan dua metode populer: **Pearson Correlation Coefficient** dan **Information Gain**.

## Fitur Analisis
* **Pra-pemrosesan Data:** Penanganan nilai null sederhana dan pemilihan subset kolom.
* **Perhitungan Pearson Correlation Coefficient:** Mengukur hubungan linear antara fitur numerik dan target.
* **Perhitungan Information Gain:** Mengukur informasi yang diberikan oleh fitur terhadap target kategorikal.
* **Visualisasi Data:** Heatmap untuk Pearson Correlation.
* **Penentuan Relevansi Fitur:** Mengidentifikasi fitur paling penting berdasarkan kedua metode.
* **Kesimpulan:** Ringkasan temuan dan implikasinya.

## Dataset
Dataset yang digunakan adalah `student_habits_performance.csv`. Untuk analisis ini, kami memilih subset dengan 6 kolom berikut:
* `study_hours_per_day`
* `social_media_hours`
* `netflix_hours`
* `attendance_percentage`
* `sleep_hours`
* `exam_score` (variabel target)

## Metodologi
1.  **Pra-pemrosesan Data:** Data dibersihkan dari nilai null.
2.  **Pearson Correlation:** Dihitung untuk semua fitur numerik terhadap `exam_score`.
3.  **Information Gain:** `exam_score` dikategorikan menjadi 3 bin (Low, Medium, High). Information Gain kemudian dihitung untuk setiap fitur terhadap target yang sudah dikategorikan ini.
4.  **Visualisasi:** Heatmap matriks korelasi dibuat untuk visualisasi hubungan antar fitur dan target.

## Hasil dan Temuan Kunci

### Pearson Correlation with Exam Score
| Fitur                 | Koefisien Korelasi Pearson |
| :-------------------- | :------------------------- |
| `study_hours_per_day` | 0.83                       |
| `social_media_hours`  | -0.17                      |
| `netflix_hours`       | -0.17                      |
| `attendance_percentage`| 0.09                     |
| `sleep_hours`         | 0.12                       |

`study_hours_per_day` menunjukkan korelasi positif yang sangat kuat, menunjukkan hubungan linear yang signifikan dengan nilai ujian.

### Information Gain with Binned Exam Score
| Fitur                 | Information Gain |
| :-------------------- | :--------------- |
| `study_hours_per_day` | 0.40             |
| `sleep_hours`         | 0.02             |
| `social_media_hours`  | 0.01             |
| `netflix_hours`       | 0.00             |
| `attendance_percentage`| 0.00             |

`study_hours_per_day` memiliki Information Gain tertinggi, mengkonfirmasi bahwa fitur ini memberikan informasi paling banyak tentang kategori nilai ujian.

### Heatmap Korelasi
![Heatmap of Pearson Correlation Matrix](generated:code_execution_image_1_1748053577.6568406.png-1527861862319175200927a8689598e18233)

### Kesimpulan
Berdasarkan kedua metode, **`study_hours_per_day`** secara konsisten terbukti menjadi fitur paling relevan dan signifikan dalam memprediksi `exam_score`. Fitur lain seperti `social_media_hours`, `netflix_hours`, `attendance_percentage`, dan `sleep_hours` menunjukkan relevansi yang jauh lebih rendah atau bahkan tidak relevan dalam konteks ini.

## Cara Menjalankan Kode
1.  Pastikan Anda memiliki Python terinstal.
2.  Instal library yang diperlukan:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
3.  Unduh dataset `student_habits_performance.csv` dan letakkan di direktori yang sama dengan skrip Python Anda.
4.  Jalankan skrip Python yang telah disediakan.

## Dependencies
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scikit-learn`

---
