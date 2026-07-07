# Log 04: Packer Detection

## Deskripsi
Mendeteksi apakah sebuah file biner telah di-*pack* atau di-*compress* untuk menyembunyikan kode asli dari *Static Analysis*.

## Indikator Utama
* **Entropy Tinggi**: Nilai entropi di atas 7.0 biasanya menandakan data terenkripsi atau terkompresi.
* **Section Names**: Nama *section* yang aneh atau tidak standar (misal: `UPX0`, `UPX1`).
* **Few Imports**: Jika program sangat besar tetapi hanya meng-*import* `LoadLibrary` dan `GetProcAddress`, kemungkinan besar itu adalah *packed file*.

## Alat Analisis
* **Detect It Easy (DiE)**: Alat terbaik untuk mengidentifikasi *packer* atau *compiler* yang digunakan.
* **PE-bear**: Melihat *section header* secara manual.

## Strategi
Jika file terdeteksi di-*pack*, kita tidak bisa melakukan *Static Analysis* secara efektif. Kita harus melakukan **Unpacking** terlebih dahulu (biasanya melalui *Dynamic Debugging*).