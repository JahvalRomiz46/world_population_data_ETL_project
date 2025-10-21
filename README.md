# Analisis Distribusi Populasi Dunia 🌍

## Data Engineering Project : Implementasi ETL Pipeline dengan Python

---

## Deskripsi & Tujuan Proyek
Proyek ini mengatasi tantangan utama *Data Engineering*: mengubah data semi-terstruktur dari web yang masih mentah menjadi data yang siap dianalisis.
-   **Sumber Data:** Wikipedia, **`List of countries and dependencies by population`**.
-   **Tujuan :** Implementasi ETL dan mengidentifikasi *insight* mengenai data populasi dunia.

---

## Tech Stack & Libraries
* **Data Collection** = `requests`, Mengambil konten HTML, mengatasi *Error 403 (Forbidden)*.
* **Data Extraction** = `BeautifulSoap`, Mengekstrak tabel HTML statis ke DataFrame.
* **Data Wrangling** = `Pandas`, Cleaning data (menghapus baris & kolom yang tidak digunakan untuk analisis, konversi tipe data, trim penulisan yang belum rapi). |
* **Load & Visualisasi** = `Matplotlib`, Membuat visual grafik.
* **Data Target** = `Pandas.to_excel`, Menyimpan data yang sudah bersih ke format '.xlsx'

---

## Pipeline
Pipeline ini dijalankan secara manual & berurutan di Google Colab.
### 1. **Extract (E):**
- Menggunakan **`requests`** dengan `User-Agent` untuk mengambil konten HTML dari URL Wikipedia.
- Menggunakan **`beautifulsoup`** untuk *parsing* dan *extraction* tabel html.

### 2. **Transform (T): Data Cleaning & Validation**
- Menghapus koma di nilai populasi, menghapus simbol `%` di nilai Percentage, dan menghapus penulisan sitasi "[1]" dari kolom Source.
- Mengkonversi kolom Date menjadi tipe datetime, kolom Population ke int, dan Percentage ke float.
- Menghapus baris pertama (World) karena tidak digunakan untuk analisis.

### 3. **Load (L): Output & Visualisasi**
-   Data Target: Mengekspor DataFrame akhir yang sudah bersih ke file Excel `.xlsx`.
-   Visualisasi: Data bersih dimuat ke **Matplotlib** untuk menghasilkan *insight* visual.

---

## Key Insights
1. Rata-rata populasi di seluruh dunia berjumlah 33.554.601 jiwa.
2. India, China, United States, Indonesia, dan Pakistan merupakan 5 negara teratas dengan populasi tertinggi. 
3. Hasil dari Pie Chart menunjukkan bahwa **45% populasi dunia hanya berada di 5 negara teratas**. Ini menunjukkan ketimpangan yang besar dan konsentrasi data yang harus dipertimbangkan dalam setiap analisis global.
4. Dari grafik distribusi populasi dengan Histogram, ditemukan bahwa mayoritas negara memiliki populasi yang kecil, dan hanya negara dengan posisi atas yang mendominasi distribusi.

---
