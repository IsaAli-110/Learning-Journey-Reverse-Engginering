# ⚙️ Log 01: Dasar Arsitektur Komputer

> *"Memahami jantung dari eksekusi program: Bagaimana CPU 'berpikir' dan memproses instruksi."*

---

## 🎯 Learning Objectives
- [ ] Memahami siklus utama eksekusi instruksi (Fetch-Decode-Execute).
- [ ] Mengenal peran penting register dalam penyimpanan data sementara.
- [ ] Membedah perbedaan mendasar arsitektur x86 (32-bit) dan x64 (64-bit).

---

## 🔄 Visualisasi Konsep: Siklus CPU
Berikut adalah gambaran sederhana bagaimana CPU mengolah perintah setiap detiknya:

```mermaid
graph LR
    A[Fetch] -->|Ambil Instruksi| B[Decode]
    B -->|Terjemahkan| C[Execute]
    C -->|Jalankan Operasi| D[Store/Writeback]
    D -->|Simpan Hasil| A

    🧠 Konsep Utama1. 
    Register: "Memori" TercepatRegister adalah lokasi penyimpanan di dalam CPU yang digunakan untuk menyimpan data yang sedang diproses secara real-time.
    RegisterFungsi Utama
    EAX/RAXAccumulator (Hasil operasi matematika & return value)
    EBX/RBXBase Register (Penyimpanan data umum)
    ECX/RCXCounter Register (Untuk perulangan/looping)
    EDX/RDXData Register (Input/Output & operasi perkalian)
    ESP/RSPStack Pointer (Alamat paling atas di stack)
    EIP/RIPInstruction Pointer (Alamat instruksi selanjutnya)
    
    2. Stack Pointer (ESP/RSP)
    Bayangkan Stack sebagai tumpukan piring. ESP/RSP selalu menunjuk ke piring paling atas.Jika kita PUSH data, Stack Pointer akan berkurang (menunjuk ke bawah/atas tumpukan).Jika kita POP data, Stack Pointer akan bertambah.
    
    3. Instruksi Dasar (Assembly)
    Instruksi adalah perintah spesifik yang dimengerti oleh CPU:
    MOV Dest, Src : Menyalin nilai dari Source ke Destination.
    PUSH Value    : Memasukkan data ke dalam Stack.POP Dest      : Mengambil data teratas dari Stack ke Destination.
    ADD/SUB       : Operasi aritmatika dasar
    
    💡 Pro-Insight (Catatan Penting)
    Penting untuk diingat: Pada arsitektur x64 (64-bit), ukuran register menjadi dua kali lipat dibanding x86 (32-bit).
    EAX (32-bit) menjadi RAX (64-bit).
    ESP (32-bit) menjadi RSP (64-bit).Selalu 
    
    periksa apakah program yang kamu analisis adalah 32-bit atau 64-bit sebelum memulai analisis, karena ini mengubah cara register digunakan!
    Status: ✅ Selesai

    ---

### Tips Tambahan untuk Kamu:
1.  **Diagram Mermaid:** Jika kamu menggunakan VS Code, pastikan kamu menginstall extension **"Markdown Preview Mermaid Support"**. Dengan begitu, diagram di atas akan langsung berubah menjadi gambar grafis yang keren di tampilan *preview* kamu.
2.  **Konsistensi:** Gaya penulisan ini akan saya pakai untuk log-log berikutnya agar repositorimu terlihat sangat rapi.

**Apakah log ini sudah cukup keren?** Kalau oke, silakan simpan (Ctrl+S) dan lanjut ke **Log 02** (Memory Model), atau ada bagian yang ingin kamu modifikasi lagi?