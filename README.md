# Pertemuan 12 - File I/O dan Error Handling

Nama: Nuril Ilmy
NIM: 2225250066
Kelas: 3E

## Tujuan
Membaca, memvalidasi, mengolah, dan menulis data file dengan Python.

## Format File Input
NIM,nilai

## Cara Menjalankan
python3 tugas/rekap_nilai_file.py

## Error yang Ditangani
- FileNotFoundError
- ValueError

## Test Case
- **Kondisi Normal**: Semua baris format `NIM,nilai` valid. 
  - *Hasil yang diharapkan:* Data terbaca dan statistik rekap ditulis ke file output dengan benar.
  - *Hasil Aktual:* Sesuai harapan.
  - *Status:* Lolos.
- **Kondisi File Hilang**: File `nilai.txt` tidak ditemukan di direktori.
  - *Hasil yang diharapkan:* Menampilkan pesan error file tidak ditemukan tanpa membuat program *crash*.
  - *Hasil Aktual:* Sesuai harapan.
  - *Status:* Lolos.
- **Kondisi Nilai Invalid**: Terdapat baris dengan nilai berupa huruf (`A004,abc`).
  - *Hasil yang diharapkan:* Baris invalid dilewati dan dilaporkan, sementara baris valid lainnya tetap diproses.
  - *Hasil Aktual:* Sesuai harapan.
  - *Status:* Lolos.

## Refleksi
Salah satu error yang ditemukan adalah **ValueError**, yang terjadi ketika program gagal mengonversi data teks nilai berupa huruf (seperti `"abc"`) menjadi tipe data angka menggunakan fungsi `float()`. Program menanganinya dengan menerapkan blok `try-except` di dalam perulangan baris file, sehingga baris yang tidak valid dapat dilewati dengan aman dan mencetak pesan peringatan tanpa menghentikan jalannya keseluruhan program.