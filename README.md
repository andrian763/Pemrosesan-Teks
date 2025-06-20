# 🎯 Klasifikasi Komentar Judi Online pada Siaran Langsung YouTube iShowSpeed

Proyek ini mengimplementasikan teknik **Pemrosesan Teks (Text Processing)** dan **Machine Learning** untuk mendeteksi dan mengklasifikasikan komentar yang mengandung promosi **judi online** pada sesi live streaming YouTube oleh kreator **iShowSpeed** di Indonesia. Fokus penelitian ini adalah untuk memberikan gambaran terhadap **penyebaran komentar ilegal** serta **analisis sentimen balasan** terhadap komentar tersebut.

---

## 📌 Latar Belakang

Siaran langsung di YouTube menjadi wadah baru bagi penyebaran konten negatif seperti **promosi judi online**, terutama di kolom komentar. Fenomena ini menjadi perhatian serius mengingat:
- Judi online dilarang keras di Indonesia
- Komentar seringkali berupa tautan, testimoni palsu, hingga ajakan eksplisit
- Penonton muda sangat rentan terhadap pengaruh konten semacam ini

Proyek ini bertujuan untuk **mengklasifikasikan komentar promosi judi online secara otomatis**, serta **menganalisis tanggapan dari komunitas penonton**.

---

## 🎯 Tujuan Proyek

- Mendeteksi komentar promosi judi online dari sesi live streaming YouTube
- Menganalisis balasan komentar dari segi **sentimen (positif, negatif, netral)**
- Membandingkan kinerja dua algoritma: **Support Vector Machine (SVM)** dan **Random Forest**
- Mendukung pengembangan sistem **moderasi komentar otomatis**

---

## 🧪 Dataset

- **Data Komentar:** dikumpulkan melalui scraping YouTube API dari video live streaming *“IRL Stream in Indonesia”*
- **Labeling:** menggunakan dataset latih dari Kaggle untuk klasifikasi awal
  - Class 0: Komentar bukan promosi judi
  - Class 1: Komentar promosi judi
- **Data Balasan:** dievaluasi dengan label sentimen (positif, netral, negatif)

---

## 🔧 Tahapan Pemrosesan

### 📥 1. Pengumpulan Data
- Scraping menggunakan Python dan YouTube Data API v3
- Komentar dan balasan dikumpulkan dari video target

### 🧹 2. Preprocessing
- Case folding
- Regex cleaning (hapus URL, tanda baca, huruf berulang)
- Stopword removal
- Stemming (Bahasa Indonesia)
- Tokenization

### 🧠 3. Feature Engineering
- **TF-IDF:** menghitung bobot kata terhadap dokumen
- **Word2Vec:** representasi vektor semantik kata

### ⚖️ 4. Split Data
- Train: 80% | Test: 20%

---

## 🧪 Model yang Digunakan

| Model               | Fitur     | Akurasi     |
|---------------------|-----------|-------------|
| SVM                 | Word2Vec  | 85.8%       |
| SVM                 | TF-IDF    | 99.7%       |
| Random Forest       | Word2Vec  | 99.9%       |
| Random Forest       | TF-IDF    | 99.9%       |

---

## 📊 Evaluasi Sentimen Balasan

| Kelas Balasan | Jumlah |
|---------------|--------|
| Positif       | 326    |
| Negatif       | 2.345  |
| Netral        | 29.731 |

> Mayoritas balasan bersifat **netral** atau kosong (NULL), sementara **balasan terhadap komentar promosi judi** cenderung lebih banyak bernada **negatif** daripada positif.

---

## 🌐 Wordcloud Analisis

- **Komentar promosi** didominasi kata: `situs`, `bonus`, `main`, `depo`, `dewi`
- **Balasan komentar promosi** banyak mengandung kata: `nan` (karena NULL) dan ekspresi negatif

---

## 🧠 Kesimpulan

- Komentar promosi judi online **tidak terlalu banyak (999 dari 32.000+)**, namun tetap signifikan.
- **Respons penonton cenderung mengabaikan komentar tersebut**, meskipun ada yang menunjukkan ketidaksukaan (sentimen negatif).
- Model **Random Forest dengan TF-IDF** memberikan hasil terbaik.
- Pendekatan ini dapat dijadikan **sistem pendukung moderasi konten otomatis**.

---

## 💼 Teknologi yang Digunakan

- Python
- Scikit-learn
- NLTK & Sastrawi
- Gensim (Word2Vec)
- YouTube API v3
- Matplotlib, Seaborn
- Pandas, NumPy

---

## 🧑‍💻 Kontributor

**Andrian Simanjuntak**  
Mahasiswa Sains Data  
Universitas [Isi Nama Kampus Anda]  
Mata Kuliah: **Pemrosesan Teks / Kecerdasan Artifisial**

---

## 📚 Referensi

- [Scikit-learn Documentation](https://scikit-learn.org/)
- [YouTube Data API](https://developers.google.com/youtube/v3)
- [Kaggle - Online Gambling Comment Dataset](https://www.kaggle.com/)

---

## ⚠️ Catatan

- Penelitian ini **tidak mendukung atau menyebarkan konten judi online**.
- Dataset digunakan hanya untuk keperluan akademik dan penelitian ilmiah.
