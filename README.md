# Sistem Deteksi dan Pelacakan Objek Dinamis

![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

Proyek ini merupakan implementasi untuk Ujian Akhir Semester mata kuliah Visi Komputer, yang membangun sebuah sistem cerdas untuk mendeteksi, melacak, dan menganalisis objek (manusia atau hewan) dari input video secara *real-time*.

## Deskripsi Proyek

Sistem ini dirancang dengan arsitektur hibrida untuk menyeimbangkan antara akurasi deteksi dan efisiensi komputasi. Ia menggunakan metode deteksi berbasis **Haar Cascade** secara periodik untuk mengidentifikasi objek baru dan beralih ke algoritma pelacakan **CSRT Tracker** yang lebih ringan untuk mengikuti pergerakan objek antar-frame.

## Fitur Utama

- **Deteksi Objek Dinamis**: Mampu mendeteksi **tubuh manusia** atau **wajah kucing** berdasarkan pilihan pengguna saat program dijalankan.
- **Pelacakan Multi-Objek**: Melacak beberapa objek secara bersamaan, masing-masing dengan ID unik.
- **Arsitektur Hibrida**: Menggabungkan deteksi periodik (setiap 10 frame) dengan pelacakan *frame-to-frame* untuk efisiensi *real-time*.
- **Analisis Kuantitatif**:
    - **Penghitung Objek**: Menampilkan jumlah total objek yang aktif terdeteksi.
    - **Pemantau Durasi**: Menghitung dan menampilkan berapa lama setiap objek berada di dalam frame.
- **Visualisasi Augmented Reality**: Menampilkan *bounding box*, ID, dan data analitik secara langsung di atas video.

## Teknologi yang Digunakan

- **Bahasa Pemrograman**: Python 3
- **Pustaka Utama**:
    - **OpenCV (`opencv-contrib-python`)**: Untuk semua operasi visi komputer (deteksi, pelacakan, pemrosesan gambar).
    - **NumPy**: Untuk operasi numerik yang efisien.
    - **SciPy**: Untuk menghitung jarak antar centroid dalam logika pencocokan objek.
- **Model Deteksi**:
    - `haarcascade_fullbody.xml`
    - `haarcascade_frontalcatface.xml`

## Petunjuk Instalasi dan Penggunaan

Pastikan Anda memiliki Python 3.8+ terinstal di sistem Anda.

**1. Clone Repository**
git clone https://github.com/askashahira/UAS_VISKOM_ObjectTracker.git

2. Instal Dependensi

# Buat virtual environment (opsional tapi direkomendasikan)
python -m venv venv
source venv/bin/activate  # Di Windows: venv\Scripts\activate

# Instal pustaka yang diperlukan
pip install opencv-contrib-python numpy scipy

3. Siapkan File
Pastikan semua file yang diperlukan berada di dalam direktori proyek:

  uas_dynamic_detector.py
  haarcascade_fullbody.xml
  haarcascade_frontalcatface.xml
  File video yang ingin Anda uji (misalnya, video_orang.mov).

4. Jalankan Program
Jalankan skrip utama dari terminal:

`python uas_dynamic_detector.py`

Program akan meminta Anda untuk memilih mode deteksi dan memasukkan nama file video.

Contoh Sesi:

--- Sistem Penghitung Orang dan Pemantau Durasi ---
Pilih objek yang ingin dideteksi:
1: Manusia (Seluruh Tubuh)
2: Hewan (Wajah Kucing)
Masukkan pilihan (1 atau 2): 1
Masukkan nama file video untuk deteksi 'Orang': video_orang.mov

Sistem dimulai untuk mendeteksi 'Orang'...
Tekan 'q' untuk keluar.

Sebuah jendela akan muncul menampilkan hasil pemrosesan video. Tekan 'q' untuk menghentikan program.

Konsep Visi Komputer yang Diimplementasikan

Proyek ini mengintegrasikan beberapa konsep inti dari perkuliahan Visi Komputer:

Image Filtering & Preprocessing: Konversi ke grayscale untuk mempercepat deteksi.

Deteksi Objek Berbasis Fitur: Implementasi langsung Haar Cascade untuk deteksi awal.

Object Tracking: Penggunaan CSRT Tracker untuk efisiensi pemrosesan video.

Analisis Data Visual: Transformasi data visual (posisi objek) menjadi data kuantitatif (jumlah, durasi).

Augmented Reality: Overlay informasi digital (teks, kotak) pada video feed.


Disusun oleh:
[ASKA SHAHIRA] - [2308107010075]
