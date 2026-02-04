# Analisis Sentimen Debat Capres 2024

Proyek ini merupakan implementasi Analisis Sentimen Komentar YouTube Debat Capres 2024 yang di unggah oleh media TV One News pada 7/1/2024 menggunakan pendekatan Natural Language Processing (NLP) dan Deep Learning. Proyek ini dikembangkan sebagai bagian dari submission Program Belajar Fundamental Deep Learning (Dicoding). 

📌 Tujuan Proyek
Tujuan utama proyek ini adalah:
- Mengumpulkan data komentar YouTube secara mandiri melalui proses scraping
- Melakukan preprocessing teks bahasa Indonesia
- Melakukan pelabelan sentimen (positif, netral, negatif)
- Membangun dan membandingkan beberapa model Deep Learning
- Mengevaluasi performa model menggunakan data uji (test set)

📂 Struktur Repository
AnalisisSentimenDebatCapres2024/
│
├── Analisis_sentimen_debat_capres2024.ipynb # Notebook utama analisis & modeling
├── scraping_youtube_tvone_py.ipynb # Script scraping komentar YouTube
├── youtube_comments_debat_capres2024.csv # Dataset hasil scraping
├── requirements.txt # Daftar library yang digunakan
└── README.md # Dokumentasi proyek

🧾 Dataset
- Sumber: Komentar YouTube Debat Capres 2024 TV OneNews (https://www.youtube.com/watch?v=UwrmlpZtVpE)
- Jumlah data: >10.000 komentar
- Bahasa: Indonesia
- Label sentimen:
1. negative
2. neutral
3. positive

Pelabelan dilakukan menggunakan pendekatan lexicon-based sentiment analysis bahasa Indonesia sebagai pseudo-label.


🧠 Arsitektur Model Deep Learning

Proyek ini menguji 5 skema model yang terdiri dari Deep Learning dan Classical Machine Learning untuk membandingkan performa analisis sentimen.

🔹 Model 1 (Baseline)
- Embedding (128 dimensi)
- Bidirectional LSTM (64 unit)
- Dropout (0.5)
- Dense Softmax (3 kelas)

🔹 Model 2 (Stacked BiLSTM)
- Embedding (128 dimensi)
- BiLSTM (64 → 32 unit)
- Dropout (0.5)
- Dense Softmax

🔹 Model 3 (Model Lebih Kompleks)
- Embedding (256 dimensi)
- BiLSTM (128 unit)
- Dense ReLU
- Dropout (0.3)
-Dense Softmax

🔹 Model 4 – Naive Bayes + TF-IDF
- Feature Extraction: TF-IDF Vectorizer
- Algoritma: Multinomial Naive Bayes
- Digunakan sebagai baseline classical machine learning
- Cocok untuk evaluasi awal performa dataset teks

🔹 Model 5 – Support Vector Machine (SVM) + CountVectorizer
- Feature Extraction: CountVectorizer
- Algoritma: Support Vector Machine (Linear Kernel)
- Digunakan sebagai pembanding classical ML yang kuat
- Menunjukkan performa yang kompetitif dibanding model deep learning

Berdasarkan hasil evaluasi pada data uji, model BiLSTM Baseline menghasilkan performa terbaik dengan test accuracy di atas 86%, mengungguli model classical machine learning maupun varian BiLSTM lainnya. Model SVM dengan CountVectorizer tetap menunjukkan performa yang kompetitif sebagai baseline classical machine learning, namun secara keseluruhan pendekatan deep learning (BiLSTM) lebih efektif dalam menangkap konteks dan dependensi kata pada teks komentar berbahasa Indonesia

👤 Author
Nazly Rafa |
Mahasiswa & Data Enthusiast

⭐ Catatan
Proyek ini dibuat untuk keperluan pembelajaran dan portofolio. Feedback dan kontribusi sangat terbuka.
