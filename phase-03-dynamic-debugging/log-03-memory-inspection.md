# Log 03: Memory Inspection

## Deskripsi
Menganalisis isi memori (RAM) saat proses sedang berjalan. Ini adalah cara terbaik untuk melihat data yang sudah didekripsi oleh program.

## Poin Utama
* **Memory Dump**: Mengambil salinan area memori tertentu ke dalam file untuk analisis lebih lanjut.
* **Strings in Memory**: Mencari informasi sensitif seperti password, kunci enkripsi, atau URL yang tidak terlihat saat statis.
* **Heap/Stack Dump**: Memeriksa isi memori dinamis untuk melihat objek atau data user yang sedang diproses.

## Tools
* **x64dbg/x32dbg**: Memiliki *Memory Map* yang sangat memudahkan inspeksi.
* **Process Hacker**: Untuk melihat *memory layout* dari proses yang sedang berjalan.