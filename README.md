# 🧠 **Analisis Perbandingan Clustering DASS (Depression Anxiety Stress) Menggunakan K-Means dan Gaussian Mixture Model (GMM)**

---

## 📋 **Deskripsi Singkat Proyek**

Proyek ini merupakan bagian dari Tugas Besar mata kuliah Pembelajaran Mesin di Program Studi Teknik Informatika. Tujuan utama dari proyek ini adalah menerapkan dan membandingkan dua teknik **clustering**, yaitu metode **K-Means dan Gaussian Mixture Model (GMM)** dalam mengelompokkan tingkat risiko depresi, kecemasan, dan stres berdasarkan data kuesioner **DASS-42** (Depression, Anxiety, Stress Scales).

---

## 📖 **Latar Belakang Masalah**

Kesehatan mental merupakan komponen penting dalam kualitas hidup, terutama bagi mahasiswa yang sedang berada pada fase transisi menuju dunia profesional. Tekanan akademik, adaptasi sosial, tuntutan ekonomi, serta ekspektasi lingkungan menjadikan kelompok ini sangat rentan mengalami gangguan mental.

Menurut World Health Organization (2022), sekitar 12,5% populasi dunia mengalami gangguan mental, dengan usia muda dewasa (termasuk mahasiswa) sebagai kelompok paling terdampak. Di Indonesia, Riskesdas 2018 mencatat bahwa 9,8% penduduk usia 15 tahun ke atas mengalami gangguan mental emosional — angka ini menunjukkan tren peningkatan dibanding tahun-tahun sebelumnya.

Kasus terkini menunjukkan situasi yang mengkhawatirkan, di FISIP UI, 60% mahasiswa baru dilaporkan mengalami masalah kesehatan mental seperti stres, *overthinking*, dan kecemasan sosial. Respon terhadap fenomena ini sudah mulai dilakukan, seperti oleh Universitas Negeri Semarang (UNNES) yang meluncurkan layanan konseling gratis “Kawan Dengar” sebagai upaya preventif dan intervensi awal terhadap tekanan psikologis mahasiswa.

Melihat kompleksitas masalah ini, pendekatan berbasis *data-driven* menjadi solusi yang menjanjikan. Salah satunya adalah melalui **teknik clustering**, metode *unsupervised learning* yang mampu mengelompokkan data berdasarkan pola tersembunyi tanpa memerlukan label. Dalam studi ini, **clustering** digunakan untuk mengelompokkan mahasiswa berdasarkan **skor survei DASS-42 (Depression Anxiety Stress Scales)** untuk memetakan tingkat risiko kesehatan mental.

Dua metode utama yang digunakan adalah:

- K-Means, yang mengelompokkan data berdasarkan kedekatan jarak ke pusat cluster.
- Gaussian Mixture Model (GMM), yang mengasumsikan data berasal dari campuran distribusi Gaussian dan membentuk cluster berdasarkan probabilitas keanggotaan.

---

## 🎯 **Tujuan Proyek**

- Mengelompokkan tingkat risiko kesehatan mental mahasiswa (berdasarkan gejala depresi, kecemasan, dan stres) menggunakan algoritma **clustering K-Means dan Gaussian Mixture Model (GMM)** berdasarkan data **hasil survei DASS**.
- Menganalisis dan membandingkan hasil pengelompokan yang diperoleh dari metode **K-Means dan GMM** dalam hal struktur cluster dan relevansi dengan kondisi kesehatan mental responden.
- Menentukan metode **clustering** yang paling optimal dalam segmentasi tingkat risiko kesehatan mental mahasiswa.

--- 

## 🗃️ **Deskripsi Dataset**

Dataset yang digunakan dalam proyek ini berjudul "Depression, Anxiety, and Stress Scales Responses (DASS-42)", diambil dari platform Kaggle. Dataset ini berisi hasil survei psikologis dari ribuan responden yang mengisi instrumen DASS-42, serta dilengkapi dengan data demografi dan kepribadian.

### Karakteristik Dataset:  

- Jumlah data: ±39.000 entri sebelum filtering
- Sumber: Survei daring global (tahun 2017–2019)
- Format: CSV
- Jumlah kolom: 172 kolom (fitur)

### Fitur Utama: 

- DASS-42 Items (Q1A–Q42A):
- 42 pertanyaan dengan skala 0–3 untuk mengukur Depresi, Kecemasan, dan Stres
- Dibagi menjadi 14 item per aspek

### Demografi Responden:

Usia (age), jenis kelamin (gender), pendidikan (education), status hubungan (relationship status), orientasi seksual (orientation), tempat tinggal (urban/rural), dan ukuran keluarga (familysize).

---

## ⚙️ **Algoritma yang Digunakan**

### K-Means Clustering  
Metode clustering berbasis centroid, mengelompokkan data berdasarkan jarak ke pusat cluster. Efektif untuk cluster dengan bentuk seragam dan jelas.

### Gaussian Mixture Model (GMM)  
Model probabilistik yang mengasumsikan data berasal dari campuran distribusi Gaussian. Lebih fleksibel dan mampu menangani cluster yang overlap.

---

## 🚀 **Panduan Menjalankan Kode**

### Prasyarat  
Pastikan sebelum menjalankan notebook, perangkat sudah memenuhi:
- Sistem operasi: Windows / macOS / Linux
- Python 3.7 atau lebih baru sudah terinstal
- Editor kode, misalnya VSCode, JupyterLab, Jupyter Notebook

### Clone Repository dari Github 

📂 **Notebook:** [ClusteringMoodie.revisi.ipynb](./notebooks/MoodieClustering_revisi.ipynb)

- Bukalah terminal atau CMD lalu unduh kode dati Github
```bash
git clone https://github.com/ayujnnti12/Clustering-Moodie.git
cd repository-name
```

### Membuat dan Mengaktifkan Environment 
```bash
python -m venv venv
venv\Scripts\activate
```

### Instal pustaka Python berikut  
`numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`, `imbalanced-learn`  

Instalasi dengan:  
```bash
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn
```

### atau menginstal pustaka menggunakan requirement.txt
```bash
pip install -r requirements.txt
```

### Menjalankan Notebook
- Jalankan cell satu per satu dengan klik tombol "Run" atau tekan Shift + Enter
- Pastikan setiap cell berjalan tanpa error
- Jika terdapat error terkait file atau data yang hilang, pastikan file pendukung sudah ada di folder yang sesuai atau unduh jika perlu
- Unduh file dataset dan letakkan di folder yang sama dengan notebook yang ingin dijalankan: [Dataset](./data/data.csv)

### Apa yang akan dilakukan pada notebook ini?
- **Eksplorasi Data (EDA)**  
  Memahami struktur data, mengecek nilai yang hilang, dan mengevaluasi distribusi kelas responden.
  
- **Pembersihan Data**  
  Menghapus data yang tidak valid menggunakan `Vocabulary Check List (VCL)`.

- **Normalisasi Data**  
  Menggunakan `StandardScaler` untuk menstandarisasi fitur agar model tidak bias karena perbedaan skala.

- **Clustering dengan K-Means dan GMM**  
  Mengelompokkan data ke dalam cluster berdasarkan fitur yang sudah diproses.

- **Visualisasi Hasil**  
  Menggunakan `PCA` untuk mereduksi dimensi dan menampilkan hasil clustering dalam bentuk scatter plot.

---

## 📊 **Contoh Hasil Output dan Visualisasi**

Pada bagian ini, penulis menyajikan contoh hasil output dan visualisasi yang dihasilkan dari penerapan algoritma **K-Means** dan **Gaussian Mixture Model (GMM)** untuk proses *clustering*, beserta evaluasi model dan visualisasi.

### Grafik Evaluasi Cluster Optimal K-Means

![Grafik Evaluasi Cluster Optimal K-Means](visualisasi/grafik_evaluasikmeans.png)

*Gambar 1: Grafik Evaluasi Cluster Optimal pada K-Means*

### Grafik Evaluasi Cluster Optimal GMM

![Grafik Evaluasi Cluster Optimal GMM](visualisasi/grafik_evaluasigmm1.png)
![Grafik Evaluasi Cluster Optimal GMM](visualisasi/grafik_evaluasigmm2.png)
![Grafik Evaluasi Cluster Optimal GMM](visualisasi/grafik_evaluasigmm3.png)
![Grafik Evaluasi Cluster Optimal GMM](visualisasi/grafik_evaluasigmm4.png)

*Gambar 2: Grafik Evaluasi Cluster Optimal pada GMM*

### Perbandingan Hasil Clustering

![Perbandingan Hasil Clustering](visualisasi/perbandingan_hasilclustering.png)

*Gambar 3: Perbandingan Hasil Clustering*

### Profil Cluster K-Means dan GMM

| ![Profil Metode](visualisasi/profilkmeans_k4.png) | ![Profil Metode](visualisasi/profilgmm_k4.png) |
|:--:|:--:|
| *Gambar 4: Profil Cluster K-Means k=4* | *Gambar 5: Profil Cluster GMM k=4* |

| ![Profil Metode](visualisasi/profilkmeans_k2.png) | ![Profil Metode](visualisasi/profilgmm_k10.png) |
|:--:|:--:|
| *Gambar 6: Profil Cluster K-Means k=2* | *Gambar 7: Profil Cluster GMM k=10* |

### Demografi dan Kepribadian per Cluster

![Demografi](visualisasi/demografikmeans_k4.png)

*Gambar 8: Demografi K-Means k=4*

![Demografi](visualisasi/demografiGMM_k4.png)

*Gambar 9: Demografi GMM k=4*

![Demografi](visualisasi/demografikmeans_k2.png)

*Gambar 10: Demografi K-Means k=2*

![Demografi](visualisasi/demografigmm_k10.png)

*Gambar 11: Demografi GMM k=10*

### Evaluasi Model

![Evaluasi Model](visualisasi/evaluasi_model.png)

*Gambar 12: Evaluasi Model*

### Heatmap Evaluasi Perbandingan Semua Metode

![Heatmap](visualisasi/heatmap_perbandingan.png)

*Gambar 13: Heatmap Perbandingan*

---

## 📝 **Kesimpulan**

Penelitian ini membandingkan dua metode **clustering**, yaitu **K-Means dan Gaussian Mixture Model (GMM)** untuk mengelompokkan tingkat risiko kesehatan mental mahasiswa berdasarkan data survei DASS-42. Terdapat empat skenario yang diuji:

- K-Means dengan k = 4 dan k = 2 (optimal)
- GMM dengan k = 4 dan k = 10 (optimal)

Evaluasi dilakukan menggunakan **Silhouette Score, Calinski-Harabasz Index, dan Davies-Bouldin Index**. Hasil menunjukkan bahwa K-Means dengan k = 2 memberikan performa terbaik dengan nilai evaluasi tertinggi di semua metrik, menandakan pemisahan *cluster* yang jelas dan stabil. Sebaliknya, GMM dengan k = 10 menunjukkan performa terburuk, kemungkinan karena *overfitting* dan asumsi distribusi Gaussian yang tidak sesuai.

Secara kualitatif, analisis menunjukkan bahwa cluster dengan kondisi mental lebih sehat umumnya berisi individu yang lebih tua, lebih stabil secara emosional, dan terbuka terhadap pengalaman baru. Kesimpulannya, K-Means (k = 2) lebih efektif dan lebih mudah diinterpretasikan untuk segmentasi kesehatan mental mahasiswa.

---
