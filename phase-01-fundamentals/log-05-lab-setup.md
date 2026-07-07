# Log 05: Setup Environment Reverse Engineering

## Alat yang Digunakan
* **Disassembler**: IDA Pro atau Ghidra (untuk membaca kode Assembly).
* **Debugger**: x64dbg (untuk analisis dinamis).
* **PE Viewer**: PE-bear atau CFF Explorer (untuk melihat struktur file).
* **Virtual Machine**: Windows 10/11 (Guest OS) yang diisolasi untuk keamanan.

## Pentingnya Isolasi
Menjelaskan pentingnya melakukan reverse engineering di dalam Virtual Machine (VM) agar sistem operasi utama (host) tetap aman dari potensi malware atau *malicious code* yang sedang dianalisis.