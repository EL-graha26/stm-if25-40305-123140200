# Tugas 2 — Analisis Audio Noise Statis

## Informasi Rekaman

- Jenis audio: Rekaman berita/suara bicara
- Format: WAV
- Sample rate awal: 48.000 Hz
- Sample rate hasil: 8.000 Hz
- Sumber noise: Kipas angin
- Frekuensi noise dominan: sekitar 70 Hz

## Analisis Noise

Berdasarkan FFT pada 0,5 detik pertama saat kondisi hening, ditemukan noise dominan sekitar 70 Hz. Noise termasuk frekuensi rendah dan terlihat terus-menerus pada spektrogram, termasuk saat tidak ada suara bicara.

Noise kemungkinan berasal dari kipas angin atau getaran motor listrik.

## Downsampling

Dilakukan perbandingan dua metode:

1. **Naive Decimation**  
   Downsampling langsung tanpa filter anti-aliasing.

2. **Resampling dengan `librosa.resample`**  
   Menggunakan filter anti-aliasing sebelum menurunkan sample rate.

Pada sample rate 8.000 Hz, frekuensi Nyquist adalah 4.000 Hz. Penggunaan filter anti-aliasing membantu mengurangi komponen frekuensi di atas batas tersebut.

## Isi Folder

- `tugas_audio_noise_statis.ipynb` — Notebook analisis
- `tugas_audio_noise_statis.pdf` — Hasil ekspor notebook
- `audio_original.wav` — Audio asli
- `audio_downsampled_naive.wav` — Hasil naive decimation
- `audio_downsampled_clean.wav` — Hasil resampling dengan anti-aliasing
- `README.md` — Dokumentasi singkat