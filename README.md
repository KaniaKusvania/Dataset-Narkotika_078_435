# Dataset-Narkotika_078_435

## 👥 Tim Penyusun
- **Kania Kusvania** – 202210370311078  
- **Hamdatul Mabruroh** – 202210370311435

Tujuan utama dari dataset ini adalah untuk menyediakan data terstruktur yang dapat digunakan dalam berbagai analisis hukum, seperti:
- Tren jumlah dan jenis barang bukti narkotika.
- Pola hukuman dan jenis vonis.
- Distribusi kasus berdasarkan lembaga peradilan.
- Pemanfaatan dalam proyek analisis teks hukum, NLP, atau machine learning.

---

## 🗂️ Struktur Dataset
| Kolom | Deskripsi |
|-------|------------|
| **No Putusan** | Nomor resmi putusan pengadilan, mencakup jenis perkara, tahun, dan kode lembaga (misal: `6/Pid.Sus/2024/PN Plk`). |
| **Lembaga Peradilan** | Nama pengadilan tempat perkara disidangkan (misal: *Palangkaraya*, *PN Denpasar*). |
| **Barang Bukti** | Deskripsi barang bukti yang disita, biasanya berupa narkotika, alat hisap, atau barang terkait. |
| **Amar Putusan** | Ringkasan keputusan akhir hakim, termasuk pernyataan bersalah dan jenis hukuman yang dijatuhkan. |

---

## Proses Ekstraksi Data
1. **Sumber Data:**  
   Dokumen putusan diambil dari situs resmi direktori putusan pengadilan (`putusan.mahkamahagung.go.id`).

2. **Metode Ekstraksi:**  
   - Parsing teks dari file `.pdf`.  
   - Pembersihan teks dengan regex untuk menghapus karakter tak relevan.  
   - Ekstraksi entitas seperti *barang bukti* dan *amar putusan* menggunakan pola kalimat tetap.  
   - Penyusunan hasil ke format tabel terstruktur `.xlsx`.

3. **Validasi:**  
   Tiap entri diperiksa secara manual untuk memastikan keakuratan identifikasi pasal dan konten putusan.

---

## 📊 Contoh Data

| No Putusan | Lembaga Peradilan | Barang Bukti | Amar Putusan |
|-------------|--------------------|---------------|----------------|
| 6/Pid.Sus/2024/PN Plk | Palangkaraya | 31 paket narkotika jenis sabu (±2.84 gram) | Menyatakan terdakwa bersalah dan menjatuhkan pidana penjara 5 tahun serta denda Rp1.000.000.000, subsider 3 bulan. |

---

## 💡 Potensi Analisis
- **Analisis Semantik:** klasifikasi isi amar putusan (ringan/sedang/berat).  
- **Named Entity Recognition (NER):** identifikasi entitas seperti nama terdakwa, lokasi, dan jenis narkotika.  
- **Data Visualization:** peta distribusi kasus narkotika antar provinsi.  
- **Legal Text Mining:** menemukan pola dalam kalimat amar putusan.
