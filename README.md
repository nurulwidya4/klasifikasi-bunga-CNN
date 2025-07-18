# 🌸 Klasifikasi Gambar Bunga Menggunakan CNN

Proyek ini merupakan bagian dari tugas akhir mata kuliah *Computer Vision* yang bertujuan untuk mengklasifikasikan gambar bunga ke dalam empat kelas: **Daffodil, Iris, Rose, dan Tulip**, menggunakan model **Convolutional Neural Network (CNN)**. Dataset awal terdiri dari 9 kelas bunga, namun hanya 4 kelas yang dipilih dan diseimbangkan ulang menggunakan teknik sampling `replace=True`.

---

## 📁 Dataset

Dataset berasal dari sumber open dataset, disimpan dalam direktori lokal `dataset_fix/` dan memiliki struktur:

Kelas yang digunakan:
- `daffodil`
- `iris`
- `rose`
- `tulip`

Jumlah gambar per kelas:
- Train: 700 gambar
- Val: 140 gambar
- Test: 140 gambar

Proses tambahan:
- Seleksi kelas
- Sampling berimbang dengan `replace=True`
- Augmentasi & normalisasi menggunakan `ImageDataGenerator`

---

## 🧠 Arsitektur CNN

Model CNN dibangun menggunakan `TensorFlow` dan `Keras` dengan struktur sebagai berikut:

| Layer             | Output Shape         | Param   |
|-------------------|----------------------|---------|
| Conv2D (32, 3x3)  | (128, 128, 32)       | 896     |
| MaxPooling2D      | (64, 64, 32)         | 0       |
| Conv2D (64, 3x3)  | (64, 64, 64)         | 18,496  |
| MaxPooling2D      | (32, 32, 64)         | 0       |
| Flatten           | -                    | 0       |
| Dense (128)       | -                    | 262,272 |
| Dropout (0.5)     | -                    | 0       |
| Dense (4, softmax)| -                    | 516     |

**Total parameter:** ±282.000  
**Optimizer:** Adam  
**Loss Function:** Categorical Crossentropy

---

## 📊 Hasil dan Evaluasi

| Metrik              | Nilai         |
|---------------------|---------------|
| Akurasi Validasi    | ± 82–88%      |
| Confusion Matrix    | ✅ Ya         |
| Classification Report | ✅ Ya       |
| Akurasi Tertinggi   | Epoch ke-10   |

Model menunjukkan performa yang baik dalam membedakan empat kelas bunga berdasarkan hasil evaluasi menggunakan confusion matrix dan classification report.

---

## 🔧 Teknologi

- Python
- Google Colab
- TensorFlow & Keras
- NumPy & Pandas
- Matplotlib & Seaborn
- Scikit-learn

---

## 📌 Cara Menjalankan

1. Buka file notebook `klasifikasi_bunga_CNN.ipynb` di [Google Colab](https://colab.research.google.com)
2. Upload folder `dataset_fix` ke Google Drive
3. Gunakan kode:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')

