
# 👣 Log 04: Execution Tracing & Flow Control

> *"Mengendalikan takdir program: Jika pintu tertutup, kita tidak perlu membongkarnya, kita cukup mengubah instruksi yang menguncinya."*

---

## 🎯 Learning Objectives
- [ ] Memahami peran instruksi `JMP` (Jump) dan `JCC` (Conditional Jump).
- [ ] Menguasai teknik manipulasi flag (`ZF`, `CF`, `SF`) untuk mengubah alur logika.
- [ ] Melakukan *Patching* instruksi secara dinamis saat runtime.

---

## 🏗️ Mekanisme Jumps dalam Assembly
Program mengambil keputusan berdasarkan kondisi tertentu. Inilah yang kita incar dalam *dynamic debugging*.

```mermaid
graph TD
    A[Instruction: CMP EAX, EBX] --> B{Z-Flag (Zero)}
    B -- EAX == EBX (ZF=1) --> C[JE / Jump Equal]
    B -- EAX != EBX (ZF=0) --> D[JNE / Jump Not Equal]
    C --> E[Alur 'Benar']
    D --> F[Alur 'Salah']

```

---

## 🧠 Teknik Manipulasi Alur

### 1. The Power of Flags

* **ZF (Zero Flag)**: Flag paling penting saat melakukan crack. Jika `CMP` membandingkan dua nilai yang sama, `ZF` akan bernilai `1`.
* **Manipulasi**: Kamu bisa memaksa `ZF` menjadi `1` atau `0` secara manual di panel *Flags* x64dbg. Ini akan membuat instruksi `JE` atau `JNE` berjalan sesuai keinginanmu meskipun inputnya salah.

### 2. Patching Instructions

Jika kamu menemukan instruksi yang menghalangi akses (misal: `JZ` yang mengarah ke pesan "Access Denied"), kamu bisa mengubah instruksi tersebut:

* **NOP (No Operation)**: Mengubah instruksi menjadi `90` (hex). Program akan "melewati" baris tersebut tanpa melakukan apa-apa.
* **Forced Jump**: Mengubah `JNE` (Jump if Not Equal) menjadi `JMP` (Always Jump) agar program selalu menuju alur sukses.

### 3. Tracing

Gunakan fitur *Run Trace* untuk merekam jejak instruksi yang dilewati program. Ini sangat membantu untuk melihat alur eksekusi saat program melakukan validasi lisensi yang kompleks.

---

## ⚠️ Professional Insight: The "Patch" Mentality

> **Jangan Merusak Struktur!**
> Saat melakukan *patching*, pastikan ukuran instruksi yang kamu ganti sama dengan instruksi baru. Jika kamu mengganti instruksi 2-byte dengan instruksi 5-byte, kamu akan merusak struktur kode di bawahnya dan membuat program *crash*. Jika tidak yakin, gunakan `NOP` saja.

---

## 💡 Key Takeaway

*Crackme adalah tentang menguasai "persimpangan jalan". Dengan memahami `EFLAGS` dan cara memodifikasi instruksi `Jump`, kamu memiliki kendali penuh atas program. Kamu tidak perlu memecahkan enkripsi jika kamu bisa memaksakan program untuk melewati fungsi validasi tersebut.*

---

*Status: ⚡ Phase 03 - Log 04 Execution Tracing Complete.*

```

---


```