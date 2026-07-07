# Log 03: Memory Management (Stack vs Heap)

## Deskripsi
Memahami perbedaan cara kerja memori saat aplikasi Windows berjalan.

## Poin Utama
* **Stack**: Digunakan untuk variabel lokal dan pemanggilan fungsi. Bersifat LIFO (Last In, First Out).
* **Heap**: Digunakan untuk alokasi memori dinamis (malloc/new).
* **Buffer Overflow**: Sering terjadi di Stack jika input tidak dibatasi.

## Kesimpulan
Memahami layout memori membantu dalam menganalisis di mana data sensitif disimpan.