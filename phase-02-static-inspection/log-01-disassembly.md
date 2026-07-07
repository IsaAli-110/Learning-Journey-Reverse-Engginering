
# 🧩 Log 01: Disassembly Basics

> *"Melihat logika mesin tanpa harus menjalankan kodenya: Teknik dasar analisis statis."*

---

## 🎯 Learning Objectives
- [ ] Memahami peran Disassembler dalam menerjemahkan biner ke Assembly.
- [ ] Mengenal alur kerja analisis statis (*Static Analysis Workflow*).
- [ ] Mampu membaca alur logika program melalui *Graph View*.

---

## 🏗️ Workflow Analisis Statis
Analisis statis adalah seni "menatap" kode. Tanpa alat yang tepat, biner hanyalah tumpukan angka heksadesimal.

```mermaid
graph TD
    A[Binary File (.exe)] --> B[Disassembler (Ghidra/IDA)]
    B --> C[Auto-Analysis]
    C --> D[Graph View / Control Flow]
    D --> E[Pseudocode C-like]

```

---

## 🧠 Komponen Utama Disassembly

### 1. The Disassembler

* **Ghidra / IDA Pro**: Alat yang bertugas mengubah *Opcode* (biner) menjadi instruksi *Assembly* yang bisa dibaca manusia.
* **Auto-Analysis**: Proses di mana alat tersebut mencari fungsi, variabel, dan struktur memori secara otomatis.

### 2. Graph View vs. Text View

* **Graph View**: Sangat krusial! Ini memvisualisasikan lompatan (`JMP`, `JE`, `JNE`) sebagai garis-garis yang menghubungkan blok kode.
* **Text View**: Menampilkan kode dalam urutan linear (sangat berguna untuk analisis *patching* atau perbaikan instruksi).

### 3. Decompiler (Pseudocode)

Ini adalah "senjata rahasia". Disassembler modern bisa mengubah *Assembly* menjadi *Pseudocode* (mirip bahasa C). Ini memudahkan kita memahami logika kompleks tanpa harus membaca tiap baris *register*.

---

## ⚠️ Professional Insight

> **Trust but Verify!**
> Jangan 100% percaya pada hasil *decompiler* (pseudocode). Kadang, *decompiler* salah menginterpretasikan tipe data atau struktur *looping*. Jika logika di pseudocode terlihat "aneh" atau tidak masuk akal, **selalu kembali ke tampilan Assembly** untuk memverifikasi apa yang sebenarnya dilakukan oleh CPU.

---

## 💡 Key Takeaway

*Disassembly adalah jembatan antara mesin dan pemahaman. Fokuslah pada 'Function Entry Points' dan 'API Calls'. Seringkali, perilaku malware atau logika tersembunyi bisa ditemukan hanya dengan melihat API apa saja yang dipanggil oleh fungsi tersebut.*

---

*Status: 🚀 Phase 02 - Log 01 Initiated.*

```
