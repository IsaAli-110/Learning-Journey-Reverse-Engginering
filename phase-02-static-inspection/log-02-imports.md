# Log 04: Imports & String Analysis

## Deskripsi
Menganalisis *Import Address Table* (IAT) dan *strings* untuk memahami kapabilitas program.

## Poin Utama
* **Imports**: Melihat fungsi DLL yang dipanggil (misal: `ws2_32.dll` -> program mungkin melakukan koneksi jaringan).
* **Strings**: Mencari teks tersembunyi seperti URL, IP address, atau pesan error yang bisa menjadi kunci analisis.

## Kesimpulan
Analisis ini sering kali memberikan gambaran instan mengenai apa yang dilakukan aplikasi sebelum kita masuk ke tahap *dynamic debugging*.