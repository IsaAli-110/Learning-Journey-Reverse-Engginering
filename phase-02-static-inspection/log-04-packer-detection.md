
# 📦 Log 04: Packer Detection

> *"Membuka kotak pandora: Bagaimana mengenali program yang menyembunyikan identitas aslinya dengan kompresi atau enkripsi."*

---

## 🎯 Learning Objectives
- [ ] Memahami apa itu *Packer* dan mengapa digunakan.
- [ ] Mampu mendeteksi tanda-tanda file yang di-pack (*Packed Binaries*).
- [ ] Menggunakan alat otomatis untuk identifikasi signature.

---

## 🏗️ Mengapa File Di-Pack?
Sebuah *packer* akan membungkus file asli dengan "wrapper". Saat dijalankan, *wrapper* tersebut akan membuka (dekompresi/dekripsi) file aslinya ke dalam memori.

```mermaid
graph LR
    A[Packed .exe] -->|Entry| B[Unpacker Stub]
    B -->|Dekripsi/Dekompresi| C[Original Code in RAM]
    C -->|Jump| D[Original Entry Point]

```

---

## 🧠 Tanda-tanda File Packed

### 1. Entropi Tinggi

Data yang terkompresi atau terenkripsi terlihat acak secara matematis. Alat seperti *Detect It Easy* (DiE) bisa mengukur **Entropi**. Jika nilainya mendekati 8, kemungkinan besar file tersebut packed/encrypted.

### 2. Import Table yang Sangat Minim

Jika program berukuran besar tetapi hanya mengimpor fungsi seperti `LoadLibrary` dan `GetProcAddress` dari `kernel32.dll`, ini adalah indikator kuat bahwa file tersebut adalah *stub* yang akan memuat fungsi asli saat dijalankan.

### 3. Nama Section yang Tidak Lazim

Waspadai nama section seperti:

* `UPX0`, `UPX1`, `UPX2` (UPX Packer)
* `ASPACK`, `FSG`, `Themida`
* Section dengan akses `RWE` (Read, Write, Execute).

---

## ⚠️ Professional Insight: The "Dead Giveaway"

> **Analisis Manual:**
> Jika kamu membuka file di Disassembler (seperti Ghidra) dan kamu melihat fungsi `main` hanya berisi sedikit instruksi sebelum melakukan *looping* panjang yang berakhir di sebuah `JMP` ke alamat memori yang jauh (berada di luar rentang kode utama), kamu sedang berhadapan dengan *Entry Point* dari sebuah *Unpacker Stub*.

---

## 💡 Key Takeaway

*Jangan buang waktu menganalisis kode hasil 'pack' karena itu hanyalah wrapper! Tugas pertamamu adalah melakukan 'Unpacking' (baik manual dengan Debugger atau otomatis) untuk mendapatkan 'OEP' (Original Entry Point) agar kamu bisa menganalisis kode yang sebenarnya.*

---

*Status: ✅ Phase 02 - Log 04 Complete*

```

---

### Tips Praktik Log 04:
1.  **Tools Wajib:** Download dan gunakan **Detect It Easy (DiE)**. Ini adalah alat terbaik untuk mendeteksi *Packer* atau *Compiler* yang digunakan pada file biner.
2.  **Latihan:** Coba cari file `.exe` yang kamu punya di komputer, jalankan di DiE, dan lihat apakah ada deteksi *Packer*.



```