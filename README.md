# 🌸 Klasifikasi Gambar Bunga Menggunakan CNN

Proyek ini merupakan bagian dari tugas akhir mata kuliah *Computer Vision* yang bertujuan untuk mengklasifikasikan gambar bunga ke dalam empat kelas: **Daffodil, Iris, Rose, dan Tulip**, menggunakan model **Convolutional Neural Network (CNN)**.

---

## 📁 Dataset

Dataset terdiri dari 9 kelas bunga, namun dalam proyek ini hanya digunakan 4 kelas:
- `daffodil`
- `iris`
- `rose`
- `tulip`

Dataset ini:
- Disimpan di Google Drive dan dipanggil di Colab
 # Path dataset di Google Drive
- dataset_path = '/content/drive/MyDrive/Colab Notebooks/dataset_bunga/flowers'
- Dipisahkan ke dalam: training, validasi, dan testing
- Telah melalui proses augmentasi dan normalisasi menggunakan `ImageDataGenerator`

---

## 🧠 Arsitektur CNN

Model CNN dibangun menggunakan `TensorFlow` dan `Keras` dengan arsitektur:

| Layer             | Output Shape      | Keterangan              |
|------------------|-------------------|-------------------------|
| Conv2D (64,3x3)   | (128, 128, 64)    | Ekstraksi fitur awal    |
| MaxPooling2D      | (64, 64, 64)      | Reduksi dimensi         |
| Conv2D (64,3x3)   | (64, 64, 64)      | Fitur lanjutan          |
| MaxPooling2D      | (32, 32, 64)      | Reduksi dimensi         |
| Dropout (0.3)     | -                 | Regularisasi            |
| Flatten           | -                 | Vektor fitur            |
| Dense (512, ReLU) | -                 | Fully connected layer   |
| Dense (4, Softmax)| -                 | Keluaran klasifikasi    |

---

## 🧪 Hasil Pelatihan

Model dilatih selama 20 epoch dan menggunakan:
- **EarlyStopping** dan **ModelCheckpoint**
- **Augmentasi gambar** untuk menghindari overfitting

📊 **Akurasi Validasi Akhir:** 100%  
📉 **Loss Validasi Terakhir:** 0.006  
✅ **Akurasi Data Uji:** 100%

Confusion Matrix dan Classification Report menunjukkan bahwa semua gambar di data uji berhasil diklasifikasikan dengan benar tanpa kesalahan.

---

## 📊 Visualisasi Hasil

- Akurasi dan loss divisualisasikan menggunakan Matplotlib
- Confusion matrix divisualisasikan dengan Seaborn
- 9 contoh gambar hasil prediksi ditampilkan dengan label aslinya dan prediksi

---

## 🔧 Teknologi

- Python
- Google Colab
- TensorFlow & Keras
- Matplotlib & Seaborn
- Scikit-learn
- Pandas, NumPy

---

## 🚀 Cara Menjalankan

1. Buka file notebook di [Google Colab](https://colab.research.google.com)
2. Mount Google Drive tempat menyimpan dataset
3. Jalankan semua cell dari atas ke bawah
4. Lihat hasil pelatihan, evaluasi, dan prediksi visual

---

## 📄 Manual Book

Dokumentasi lengkap tersedia dalam file `MANUAL BOOK.docx`  
Berisi latar belakang, teori, implementasi, hasil, pembahasan, dan kesimpulan proyek ini.

---

## 👩‍💻 Disusun oleh

**Siti Nurul Widyaningsih**  
NIM: TK0122013  
Program Studi Teknik Komputer  
Universitas Muhammadiyah Karanganyar – 2025

---
📄 Untuk melihat isi notebook secara visual, buka melalui Google Colab:
[Klik untuk buka di Google Colab](https://colab.research.google.com/github/nurulwidya4/klasifikasi-bunga-CNN/blob/main/klasifikasi_bunga_CNN.ipynb)


## 💡 Catatan

- Model ini dapat dikembangkan untuk mendeteksi lebih banyak jenis bunga (hingga 9 kelas)
- Bisa dideploy ke web-app dengan Flask atau Streamlit untuk klasifikasi gambar secara interaktif
