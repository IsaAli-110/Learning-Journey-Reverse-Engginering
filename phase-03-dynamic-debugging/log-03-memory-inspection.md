
# 💾 Log 03: Memory Inspection

> *"Jika kode adalah instruksinya, maka memori adalah perpustakaan datanya. Temukan di mana program menyimpan rahasianya."*

---

## 🎯 Learning Objectives
- [ ] Memahami organisasi memori dalam proses (Stack vs Heap).
- [ ] Mampu membaca dan menafsirkan data di *Hex Dump*.
- [ ] Menggunakan *Memory Map* untuk mengidentifikasi area yang bisa ditulis (Writable) atau dieksekusi (Executable).

---

## 🏗️ Struktur Memori Proses
Dalam setiap biner yang berjalan, memori dibagi menjadi beberapa area utama:

```mermaid
graph TD
    A[Process Memory] --> B[Stack (Data Sementara)]
    A --> C[Heap (Alokasi Dinamis)]
    A --> D[Data/Code Section (Statis)]

```

---

## 🧠 Teknik Inspeksi Memori

### 1. Hex Dump

Panel ini menampilkan data dalam format *Hexadecimal* di sebelah kiri dan representasi *ASCII* di sebelah kanan.

* **Pencarian**: Jika kamu mencari *password*, kamu tidak akan menemukannya di kode Assembly, melainkan di *Hex Dump* tepat di alamat yang ditunjuk oleh *register* input.
* **Interpretasi**: Ingat *Endianness*! Data dalam memori Windows (x86) biasanya tersimpan dalam *Little-Endian*.

### 2. Stack vs Heap

* **Stack**: Tempat variabel lokal dan alamat kembali (*return address*) disimpan. Sering menjadi target serangan *Buffer Overflow*.
* **Heap**: Digunakan untuk alokasi memori dinamis (`malloc`). Data besar seperti gambar atau teks yang di-input pengguna sering berakhir di sini.

### 3. Memory Map (The Big Picture)

Gunakan fitur *Memory Map* di debugger untuk melihat permission setiap bagian memori:

* `R` (Read): Bagian yang hanya bisa dibaca.
* `W` (Write): Bagian yang bisa diubah (tempat menyimpan variabel).
* `X` (Execute): Bagian yang berisi kode mesin yang bisa dijalankan CPU.

---

## ⚠️ Professional Insight: Memory String Tracking

> **Tips Mencari Flag:**
> Saat kamu memasukkan *input* ke program, jangan hanya mencari di *register*. Gunakan fitur "Follow in Dump" pada alamat memori yang ditunjuk oleh register input. Seringkali, kamu akan melihat *input*-mu tertulis di memori tepat sebelum fungsi pembanding (`CMP`) dijalankan.

---

## 💡 Key Takeaway

*Debugger memungkinkan kamu melihat isi memori secara langsung. Jika sebuah program melakukan enkripsi pada *key*, jangan mencoba memecahkan algoritmanya. Tunggu sampai program tersebut mendekripsi *key*-nya sendiri di memori, lalu intip di sana!*

---

*Status: ⚡ Phase 03 - Log 03 Memory Inspection Complete.*

```

---

### Tips Praktik untuk Log 03:
1.  **Observasi:** Di x64dbg, klik kanan pada register (misal `ESP` atau `EAX`) dan pilih **"Follow in Dump"**. Ini adalah cara tercepat untuk melihat data mentah yang sedang diproses oleh register tersebut.
2.  **Visual:** Perhatikan perubahan warna di panel *Hex Dump*. Setiap kali data diperbarui, debugger akan menandainya, memudahkanmu melacak perubahan variabel.

```