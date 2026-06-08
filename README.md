# Introduction to Machine Learning with Python

Repository ini berisi catatan, contoh kode, visualisasi, dan rangkuman praktis yang disusun berdasarkan buku **"Introduction to Machine Learning with Python: A Guide for Data Scientists"** by Andreas C. Müller & Sarah Guido.

Link buku : https://drive.google.com/file/d/1bitlEHE6Syb__5SUA7VOCVKGvzbhYpqO/view?usp=drive_link

Repository ini dibuat untuk kebutuhan pembelajaran mata kuliah Machine Learning (ML) dan berfokus pada implementasi praktis menggunakan library `scikit-learn`.

---

## 📚 Ringkasan Materi per Chapter (Chapter 1 - 8)

### 📌 Chapter 1: Introduction
* **Fokus Utama:** Pengenalan konsep dasar machine learning dan penyiapan ekosistem Python.
* **Topik Kunci:**
  * Perbedaan antara *Supervised Learning* dan *Unsupervised Learning*.
  * Pemahaman peran data historis dalam melatih model.
  * Pengenalan library utama: `NumPy`, `SciPy`, `matplotlib`, `pandas`, dan `scikit-learn`.
  * Studi kasus pertama: Klasifikasi spesies bunga Iris menggunakan algoritma *k-Nearest Neighbors* (k-NN).
* **Mengapa Penting:** Menaruh dasar pemahaman alur kerja ML paling dasar—dari memuat dataset hingga melakukan evaluasi performa model pertama kali menggunakan pembagian data latih (*train*) dan data uji (*test*).

---

### 📌 Chapter 2: Supervised Learning
* **Fokus Utama:** Pemodelan terarah untuk tugas Klasifikasi (Classification) dan Regresi (Regression).
* **Topik Kunci:**
  * Konsep penting: *Generalization*, *Overfitting* (model terlalu kompleks), dan *Underfitting* (model terlalu sederhana).
  * Pembahasan mendalam berbagai algoritma klasik:
    * **k-Nearest Neighbors (k-NN):** Sederhana, berbasis jarak tetangga terdekat.
    * **Linear Models:** Regresi Linear, Ridge Regression (L2 regularization), Lasso (L1 regularization), dan Regresi Logistik untuk klasifikasi.
    * **Naive Bayes Classifiers:** Sangat cepat untuk klasifikasi data berdimensi tinggi.
    * **Decision Trees:** Intuitif dan mudah divisualisasikan, tetapi rentan overfitting.
    * **Ensemble Methods:** Penggabungan beberapa model pohon (*Random Forests* dan *Gradient Boosted Decision Trees*) untuk kestabilan dan akurasi tinggi.
    * **Support Vector Machines (SVM):** Klasifikasi berbasis pencarian batas keputusan (hyperplane) optimal dengan trik kernel untuk data non-linear.
    * **Neural Networks (MLP):** Model pembelajaran mendalam yang fleksibel untuk pola kompleks.
* **Mengapa Penting:** Memberikan pemahaman kapan harus memilih algoritma tertentu berdasarkan karakteristik dataset dan batasan komputasi.

---

### 📌 Chapter 3: Unsupervised Learning and Preprocessing
* **Fokus Utama:** Eksplorasi data tanpa label pendamping dan transformasi fitur sebelum pemodelan.
* **Topik Kunci:**
  * **Preprocessing & Scaling:** Transformasi skala fitur numerik agar bernilai seragam menggunakan `MinMaxScaler`, `StandardScaler`, `RobustScaler`, dan `Normalizer`.
  * **Dimensionality Reduction:**
    * *Principal Component Analysis (PCA):* Menemukan komponen utama untuk mereduksi dimensi sekaligus visualisasi.
    * *Non-Negative Matrix Factorization (NMF):* Mereduksi dimensi dengan batasan nilai non-negatif (cocok untuk analisis citra/teks).
    * *t-SNE:* Visualisasi data berdimensi tinggi ke dalam ruang 2D/3D secara non-linear.
  * **Clustering (Pengelompokan):**
    * *k-Means:* Mengelompokkan berdasarkan pusat kluster (centroid).
    * *Agglomerative Clustering:* Pengelompokan hierarkis membentuk dendrogram.
    * *DBSCAN:* Pengelompokan berbasis kepadatan sampel untuk mendeteksi outlier dan kluster berbentuk tidak beraturan.
* **Mengapa Penting:** Membantu memadatkan informasi data, mendeteksi pola tersembunyi, dan memastikan model jarak seperti k-NN dan SVM bekerja secara optimal tanpa bias skala.

---

### 📌 Chapter 4: Representing Data and Engineering Features
* **Fokus Utama:** Mengubah representasi fitur agar lebih informatif bagi algoritma machine learning.
* **Topik Kunci:**
  * **Categorical Variables:** Mengubah teks kategori menjadi kolom biner melalui *One-Hot Encoding* menggunakan `OneHotEncoder` atau `pandas.get_dummies()`.
  * **Numeric Categories:** Membedakan angka kontinu dari angka yang bertindak sebagai kode label kategori.
  * **Binning & Discretization:** Membagi fitur kontinu menjadi beberapa interval (bin) untuk membantu model linear menangkap hubungan non-linear.
  * **Interaction & Polynomial Features:** Membuat fitur baru dengan mengalikan atau memangkatkan fitur asli demi memperkaya fleksibilitas model linear.
  * **Nonlinear Transformations:** Menerapkan fungsi matematika seperti logaritma (`log1p`) atau eksponensial pada data yang distribusinya condong/miring (*skewed*).
* **Mengapa Penting:** Terkadang, merekayasa representasi fitur yang tepat berdampak jauh lebih besar pada performa model dibandingkan sekadar mencari parameter algoritma terbaik.

---

### 📌 Chapter 5: Model Evaluation and Improvement
* **Fokus Utama:** Teknik evaluasi kualitas generalisasi model secara andal dan optimisasi parameter.
* **Topik Kunci:**
  * **Cross-Validation:** Validasi silang (*k-Fold*, *Stratified k-Fold*, *Leave-One-Out*, *Shuffle-Split*) untuk menjamin kestabilan skor evaluasi.
  * **Grid Search:** Mengotomatiskan pencarian kombinasi parameter optimal secara komprehensif menggunakan `GridSearchCV`.
  * **Evaluation Metrics:**
    * *Klasifikasi:* Akurasi, *Confusion Matrix*, *Precision*, *Recall*, *F1-score*, kurva ROC, dan skor AUC.
    * *Regresi:* Koefisien determinasi ($R^2$) dan Mean Squared Error (MSE).
* **Mengapa Penting:** Mencegah optimisme berlebih akibat kesalahan evaluasi (*target leakage*) dan memastikan performa model stabil saat dihadapkan pada data baru di dunia nyata.

---

### 📌 Chapter 6: Algorithm Chains and Pipelines
* **Fokus Utama:** Menyusun urutan langkah preprocessing dan pemodelan ke dalam satu alur kerja terpadu.
* **Topik Kunci:**
  * Penggunaan class `Pipeline` untuk mengemas preprocessing (seperti scaling/encoding) dan estimator.
  * Menghindari kebocoran data (*data leakage*) selama proses validasi silang (cross-validation).
  * Melakukan pencarian parameter secara simultan untuk preprocessing dan estimator menggunakan grid search.
  * Fleksibilitas pipeline untuk mencoba kombinasi algoritma yang berbeda secara otomatis.
* **Mengapa Penting:** Menghindari bug fatal di mana data uji tidak sengaja memengaruhi statistik data latih (misal saat kalkulasi mean/std deviasi pada penskalaan), serta membuat kode produksi menjadi bersih dan modular.

---

### 📌 Chapter 7: Working with Text Data
* **Fokus Utama:** Representasi data berbentuk teks (Natural Language Processing dasar) agar dapat diproses oleh model.
* **Topik Kunci:**
  * **Bag-of-Words (BoW):**
    * Tokenisasi (pemisahan kata).
    * Pembuatan kosakata (*vocabulary*).
    * Pembentukan matriks frekuensi kata menggunakan `CountVectorizer`.
  * **TF-IDF Scaling:** Memberi bobot kata berdasarkan seberapa informatif kata tersebut dalam suatu dokumen dibanding dokumen lainnya.
  * **Pembersihan Teks:** Menghilangkan kata umum tanpa makna (*stop words*) dan teknik normalisasi kata.
  * **Sentiment Analysis:** Menerapkan model klasifikasi linear pada data teks berskala besar.
* **Mengapa Penting:** Mengubah teks bebas yang tidak terstruktur menjadi bentuk representasi matriks numerik yang efisien (*sparse matrix*) untuk dipelajari oleh model klasifikasi/regresi.

---

### 📌 Chapter 8: Wrapping Up
* **Fokus Utama:** Strategi praktis dalam merancang proyek machine learning dari hulu ke hilir.
* **Topik Kunci:**
  * Langkah-langkah mendefinisikan masalah bisnis/akademis ke dalam format ML.
  * Pengumpulan data, pemantauan kualitas data, dan pentingnya domain knowledge.
  * Memulai dengan baseline sederhana sebelum beralih ke model yang kompleks.
  * Mengomunikasikan hasil prediksi model kepada pihak non-teknis.
  * Strategi menangani dataset skala besar (*out-of-core learning*, komputasi paralel).
* **Mengapa Penting:** Memberikan peta jalan yang realistis untuk mengaplikasikan ilmu machine learning pada masalah industri nyata, bukan sekadar menyelesaikan dataset akademis yang bersih.

---

## 🛠️ Stack Teknologi & Prasyarat
Untuk menjalankan notebook dan file `.py` di repository ini, pastikan Anda telah menginstal beberapa library Python berikut:

* **Python** (versi 3.8 ke atas direkomendasikan)
* **NumPy** & **pandas** (pustaka manipulasi data)
* **matplotlib** & **Seaborn** (visualisasi data)
* **scikit-learn** (library machine learning utama)
* **mglearn** (library pembantu visualisasi bawaan buku)

Anda dapat menginstal library di atas menggunakan perintah berikut di terminal:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn mglearn
```
