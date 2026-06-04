# Vitara Dashboard Analitik

Vitara Dashboard adalah aplikasi Streamlit untuk mengeksplorasi, memfilter, dan
memvisualisasikan dataset yang digunakan dalam pengembangan fitur AI Vitara.
Dashboard ini berdiri sendiri dan tidak memerlukan frontend, backend, maupun AI
service untuk dijalankan.

## Fitur Dashboard

| Dashboard | Kegunaan |
| --- | --- |
| **NLP** | Menampilkan distribusi emosi, tingkat stres, word cloud, insight, dan contoh teks jurnal |
| **Keystroke** | Menganalisis kecepatan mengetik, tingkat stres, backspace rate, dan variasi pola mengetik |
| **Sleep Scoring** | Menampilkan kualitas tidur, durasi, hutang tidur, interupsi, dan korelasinya |
| **Food Vision** | Menampilkan distribusi kelas makanan dan sampel gambar dari dataset |

Setiap dashboard menyediakan filter interaktif melalui sidebar serta metrik dan
grafik yang diperbarui berdasarkan data terpilih.

## Teknologi

- Python
- Streamlit
- Pandas
- Plotly
- Matplotlib
- WordCloud
- gdown

## Prasyarat

Pastikan perangkat telah memiliki:

- Python 3.10 atau lebih baru
- pip
- Koneksi internet untuk mengambil dataset dari Google Drive

## Cara Menjalankan

Jalankan perintah berikut dari root repositori:

```powershell
cd dashboard
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python -m streamlit run main.py
```

Untuk macOS atau Linux, aktifkan virtual environment dengan:

```bash
source .venv/bin/activate
```

Setelah aplikasi berjalan, buka URL yang ditampilkan Streamlit, biasanya
`http://localhost:8501`.

## Sumber Data

Dataset NLP, keystroke, sleep scoring, dan metadata Food Vision dibaca dari
Google Drive saat dashboard dijalankan. Sampel gambar Food Vision tersedia di
`Dataset/FoodVision/sample_images` dan dapat diunduh otomatis apabila belum ada.

## Struktur Direktori

```text
dashboard/
|-- assets/                         # Gambar pendukung dashboard
|-- Dataset/FoodVision/
|   `-- sample_images/              # Sampel gambar makanan
|-- modules/
|   |-- food.py                     # Dashboard Food Vision
|   |-- health.py                   # Dashboard Sleep Scoring
|   |-- keystroke.py                # Dashboard dinamika mengetik
|   `-- nlp.py                      # Dashboard NLP
|-- main.py                         # Entry point dan navigasi Streamlit
|-- requirements.txt                # Dependensi Python
`-- README.md                       # Dokumentasi dashboard
```

## Pemecahan Masalah

### Dataset gagal dimuat

Pastikan perangkat terhubung ke internet dan tautan Google Drive sumber data
dapat diakses.

### Modul Python tidak ditemukan

Pastikan virtual environment aktif dan seluruh dependensi telah terpasang:

```bash
python -m pip install -r requirements.txt
```

### Aset atau gambar tidak ditemukan

Jalankan Streamlit dari direktori `dashboard` agar seluruh path relatif dapat
ditemukan dengan benar.
