# Log 04: Tracing & Logging

## Deskripsi
Merekam jejak langkah demi langkah (*instruction tracing*) dari alur eksekusi sebuah program.

## Kegunaan
* **Debugging Logic**: Sangat membantu saat kita tidak tahu kenapa program melompat ke fungsi tertentu.
* **API Tracing**: Mencatat semua panggilan fungsi API Windows (seperti `CreateFile`, `RegOpenKey`, `ws2_32.send`) secara otomatis.
* **Code Coverage**: Melihat bagian mana saja dari kode biner yang benar-benar dieksekusi.

## Tips
Jangan melakukan *tracing* terlalu lama karena akan menghasilkan *log* yang sangat besar. Fokuskan *tracing* pada fungsi yang mencurigakan saja (misalnya fungsi pengecekan lisensi atau algoritma dekripsi).