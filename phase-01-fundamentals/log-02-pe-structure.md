# Log 02: Memahami Portable Executable (PE) Structure

## Deskripsi
Mempelajari format file `.exe` dan `.dll` pada sistem operasi Windows agar kita tahu bagaimana OS memuat program ke dalam memori.

## Komponen Utama PE Header
1. **DOS Header**: Bagian awal yang berisi tanda tangan `MZ`.
2. **NT Headers**: Berisi informasi penting seperti `File Header` (arsitektur CPU) dan `Optional Header` (Entry Point, Image Base).
3. **Section Table**: Daftar bagian-bagian file (seperti `.text` untuk kode, `.data` untuk variabel global).

## Mengapa Ini Penting?
Tanpa memahami struktur PE, kita tidak akan bisa mengetahui di mana sebuah program mulai dijalankan (*Entry Point*) atau di mana data tersimpan.

## Alat Analisis yang Digunakan
* **PE-bear** atau **CFF Explorer**: Digunakan untuk melihat isi *header* secara visual.
* **Dumpbin**: Perintah CLI untuk menampilkan informasi struktur file.

## Kesimpulan
PE structure adalah peta jalan bagi *Reverse Engineer* untuk membedah bagaimana aplikasi Windows disusun dan diinisialisasi oleh sistem operasi.