# _Optimasi Penjadwalan Rapat Komite Menggunakan Algoritma Greedy untuk Efisiensi Penggunaan Ruangan_

**Program 1**
[![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1DsTxBywdF8AWQzffikzRj29ZAtTc1pVg?usp=sharing)

**Program 2**
[![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1TtfkD6nXbrkMWukomyyFJCvBl38JIR1G?usp=sharing)

## Deskripsi
 Dalam satu bulan sejumlah komite dewan akan melaksanakan rapat yang dilaksanakan di tempat yang sama yaitu ruang pertemuan komite dewan. Setiap komite dewan memiliki data yang mencakup _tanggal_ pelaksanaan rapat, _waktu mulai_ rapat, _waktu selesai_ rapat dan _topik_ pembahasan rapat. Beberapa komite dewan memiliki jadwal yang bertabrakan, sehingga untuk menanggulanginya program ini dirancang untuk membantu mengoptimalkan penjadwalan rapat dengan pendekatan algoritma greedy.
 
## Representasi Ruang Keadaan
- **Ruang keadaan**: Semua kemungkinan konfigurasi jadwal rapat yang dapat terjadi selama satu bulan.
- **Keadaan awal**: Semua jadwal rapat dalam satu bulan yang diinginkan oleh setiap komite (termasuk jadwal yang bertabrakan).
- **Keadaan tujuan**: Konfigurasi jadwal rapat yang optimal, yaitu memaksimalkan jadwal rapat yang kompatibel, sehingga penggunaan ruang rapat lebih efisien.
- **Operator/Tindakan**: Menentukan rapat yang akan dijadwalkan berdasarkan pada beberapa kriteria/kondisi (pendekatan algoritma greedy).
    - **Kriteria**: Rapat ke _i_ dan ke _j_ dianggap **kompatibel** jika interval [_s i_ , _f i_] dan [_s j_ , _f j_] tidak beririsan/bertabrakan.
    - **Tindakan**: Jadwal rapat diurutkan berdar waktu selesai terawal, pada setiap langkah pilih jadwal yang mulainya lebih besar atau sama dengan waktu selesai rapat yang sudah dipilih sebelumnya.
- **Batasan**: Penjadwalan ulang rapat yang tidak terselenggara karena bertabrakan dengan rapat lain tidak diperhitungkan, pendekatan algoritma greedy berdasarkan waktu selesai rapat, tidak mempertimbangkan prioritas komite dan topik.
- **Solusi**: Urutan rapat yang dapat dijadwalkan secara optimal berdasarkan kriteria greedy.

## Pendekatan Algoritma Greedy
- Algoritma greedy digunakan pada kasus ini karena mudah dipahami dan diimplemetasikan. 
- Pada setiap langkahnya dipilih solusi lokal yang terbaik (memilih rapat dengan waktu selesai terawal). Dalam permasalahan pemilihan kegiatan seperti penjadwalan, solusi lokal tersebut akan membantu mencapai solusi keseluruhan yang cukup optimal, yaitu memaksimalkan jumlah rapat tanpa bertabrakan. 

## Fitur
- Input CSV: Program membaca input file CSV yang memuat informasi rapat (nama komite, tanggal, waktu mulai, waktu selesai, dan topik). ----> **Program 1**
- Input manual: Program menjalankan jumlah rapat dan informasi data setiap rapat yang di inputkan secara manual saat itu juga. ----> **Program 2**
- Algoritma Greedy: Program mengurutkan aktivitas berdasarkan tanggal terawal dan waktu selesai rapat paling awal, sehingga tidak ada jadwal bertabrakan.
- Output: Program menampilkan jadwal terpilih yang tidak bertabrakan disertai jumlah total rapat terpilih yang akan terselenggara.

## Prasyarat
Sebelum menjalankan program, pastikan bahwa:
- Python 3.x sudah terinstall.
- Library **pandas** untuk membaca file CSV.
- Library **datetime** untuk memproses data waktu.

## Input dan Output Program
Program ini menyediakan 2 alternatif input yang dapat dieksekusi
- Program 1: Input berupa file CSV yang berisi 50 data jadwal rapat komite.
- Program 2: Input manual berupa jumlah rapat yang akan dilaksanakan beserta informasi untuk setiap rapat.
### Input  Program 1
File CSV yang memiliki atribut sebagai berikut:
- **Name**: Nama komite yang menyelenggarakan rapat.
- **Date**: Tanggal rapat dalam format YYYY-MM-DD.
- **Start**: Waktu mulai rapat dalam format HH:MM.
- **Finish**: Waktu selesai rapat dalam format HH:MM.
- **Topic**: Topik rapat yang dibahas.

### Input Program 2 
Input dilakukan secara manual yang mencakup:
- **Masukkan Jumlah Rapat**: Masukkan total jadwal rapat yang akan diselenggarakan dalam format integer

Masukkan informasi data rapat ke-n:
- **Nama Komite**: Komite yang akan mengadakan rapat.
- **Tanggal Rapat**: Tanggal rapat dalam format YYYY-MM-DD.
- **Waktu Mulai**: Waktu mulai rapat dalam format HH:MM.
- **Waktu Selesai**: Waktu selesai rapat dalam format HH:MM.
- **Topik Pembahasan**: Topik rapat yang dibahas.

### Output
Hasil output untuk program 1 dan 2 sama yaitu berupa hasil jadwal yang dioptimalkan yang mencakup informasi setiap rapat beserta total jumlah rapat yang di optimalkan

## Struktur Program
1. **Rapat Class**: Memuat atribut rapat, mencakup _name_, _date_, _start_time_, _end_time_, dan _topic_. 
2. **baca_dari_csv()**: Membaca file CSV dan mengkonversi kolom _Date_, _Start_, dan _Finish_ menjadi tipe data **datetime** di **Program 1**
    **masukkan_rapat()**: Menginput data rapat secara manual yang berisi _jumlah_rapat_, dan informasi data untuk setiap rapat di **Program 2**
4. **jadwal_rapat_max()**: pendekatan algoritma greedy untuk memilih jadwal rapat optimal yang tidak bertabrakan.
5. **groub_by_date()**: Mengelompokkan rapat berdasarkan tanggal agar terstruktur.
6. **display_schedule()**: Menampilkan hasil jadwal yang terpilih beserta jumlah total rapat yang akan terselenggara.
7.  **main()**: Menginputkan file CSV yang akan di eksekusi.

## Cara Menjalankan Program
### Program 1
1. Install persyaratan: Library pandas dan datetime, python 3.x (alternatif lain: Google Colab).
2. Siapkan file CSV: Pastikan sesuai dengan format yang dibutuhkan.
3. Jalankan Program  
4. Masukkan path file CSV: Gunakan File CSV terlampir yaitu activity_dataset.csv
5. Lihat hasil outputnya: Program akan menampilkan hasil jadwal yang tidak bertabrakan.

### Program 2
1. Install persyaratan: Library pandas dan datetime, python 3.x (alternatif lain: Google Colab).
3. Jalankan Program  
4. Masukkan jumlah rapat dan informasi data untuk setiap rapat.
5. Lihat hasil outputnya: Program akan menampilkan hasil jadwal yang tidak bertabrakan.

_**Program 1** dan **Program 2** sudah terlampir di atas dan dapat di akses melalui Google Colab_

## Credit
Ismi Nurul Na'imah  
(24/541118/PPA/06824)
