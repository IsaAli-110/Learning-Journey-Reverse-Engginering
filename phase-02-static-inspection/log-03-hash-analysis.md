# Log 03: Hash Analysis

## Deskripsi
Proses pembuatan "sidik jari" unik dari file biner menggunakan algoritma kriptografi.

## Mengapa Dilakukan?
1. **Identifikasi Unik**: File yang diubah 1 bit saja akan menghasilkan hash yang berbeda.
2. **Verifikasi**: Memastikan file yang dianalisis sama dengan yang dilaporkan di laporan teknis atau *threat intelligence*.

## Algoritma Umum
* **MD5**: Cepat, tapi tidak aman dari *collision*.
* **SHA-256**: Standar industri untuk keamanan saat ini.

## Tools
* **PowerShell**: `Get-FileHash <filename> -Algorithm SHA256`
* **VirusTotal**: Untuk memeriksa apakah hash file sudah dikenal sebagai *malware* atau *clean*.