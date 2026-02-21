# Analisis Sentimen: Fenomena "Tembok Ratapan Solo" (2026)

## Background

Project ini dibuat untuk tracking dan menganalisis percakapan publik terkait fenomena viral **"Tembok Ratapan Solo"** pada Februari 2026.

Tujuan utamanya adalah mengetahui apakah fenomena ini berpotensi menjadi krisis reputasi yang serius, atau hanya sebatas budaya digital berupa meme, humor, dan kreativitas netizen.

---

## Objective

* Mengukur proporsi kritik negatif yang serius dibandingkan dengan konten bercanda.
* Memvalidasi apakah diperlukan tindakan dari tim PR/Humas.
* Membangun sistem alert otomatis jika sentimen negatif harian melewati ambang batas aman.

---

## Tools & Tech Stack

* **Bahasa**: Python
* **Data Handling & Visualisasi**: Pandas, Matplotlib
* **Model Sentimen**: IndoBERT (via Hugging Face) untuk klasifikasi sentimen Bahasa Indonesia

---

## How It Works (Alur Project)

### 1. Data Collection

Mengumpulkan ±5.000 percakapan dari:

* X (Twitter)
* YouTube

### 2. Text Preprocessing

Membersihkan data dengan:

* Menghapus URL
* Menghapus mention (@username)
* Menghapus karakter khusus dan noise
* Normalisasi teks

Tujuannya agar model NLP dapat membaca konteks dengan lebih akurat.

### 3. Sentiment Prediction

Teks yang telah dibersihkan diproses menggunakan model **IndoBERT** untuk diklasifikasikan menjadi:

* Positif
* Netral
* Negatif

### 4. Sarkasme Correction (Post-Processing Logic)

Model AI sering salah memahami sarkasme atau humor.

Contoh:

> "Kreatif banget sindirannya"

Bisa terbaca negatif oleh model, padahal konteksnya apresiasi humor.

Solusi:

* Menambahkan rule-based post-processing
* Keyword adjustment untuk konteks sarkasme
* Validasi manual pada sampel data

### 5. Monitoring & Alert System

Sistem monitoring harian dibuat untuk:

* Menghitung persentase sentimen negatif per hari
* Mengaktifkan alert jika sentimen negatif > 35%

Threshold krisis ditetapkan pada 35%.

---

## Key Findings

Setelah proses klasifikasi dan koreksi kontekstual, diperoleh hasil akhir:

| Sentimen | Persentase |
| -------- | ---------- |
| Positif  | 49.0%      |
| Netral   | 32.4%      |
| Negatif  | 18.6%      |

### Interpretasi

* **Positif (49.0%)**
  Dominan. Berisi apresiasi, humor, meme, dan kreativitas digital.

* **Netral (32.4%)**
  Informasi, pertanyaan lokasi, atau partisipasi tren.

* **Negatif (18.6%)**
  Kritik serius atau sindiran tajam.

---

## Kesimpulan

Status: **Aman**

Fenomena ini lebih condong ke arah hiburan dan budaya digital.

Dengan sentimen negatif hanya sebesar **18.6%** (jauh di bawah ambang batas krisis 35%), tidak diperlukan intervensi komunikasi atau strategi PR yang serius.

Monitoring tetap berjalan
