# Log 01: Breakpoints & Execution Control

## Deskripsi
Breakpoints adalah teknik untuk menghentikan program di instruksi tertentu.

## Jenis Breakpoint
* **Software Breakpoint (`INT 3` / `0xCC`)**: Mengganti instruksi asli dengan instruksi interrupt.
* **Hardware Breakpoint**: Menggunakan register debug CPU (sangat berguna untuk mendeteksi perubahan data di memori).
* **Memory Breakpoint**: Menghentikan program saat memori dibaca atau ditulis.