# _Optimasi Penjadwalan Rapat Komite Menggunakan Algoritma Greedy untuk Efisiensi Penggunaan Ruangan_

**Program 1**
[![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1DsTxBywdF8AWQzffikzRj29ZAtTc1pVg?usp=sharing)

**Program 2**
[![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1TtfkD6nXbrkMWukomyyFJCvBl38JIR1G?usp=sharing)

## Deskripsi
 Dalam satu bulan sejumlah komite dewan akan melaksanakan rapat yang dilaksanakan di tempat yang sama yaitu ruang pertemuan komite dewan. Setiap komite dewan memiliki data yang mencakup tanggal pelaksanaan rapat, waktu mulai rapat, waktu selesai rapat dan topik pembahasan rapat. Beberapa komite dewan memiliki jadwal yang bertabrakan, sehingga untuk menanggulanginya program ini dirancang untuk membantu mengoptimalkan penjadwalan rapat dengan pendekatan algoritma greedy.
 
## Representasi Ruang Keadaan
- Komite dewan: Setiap komite memiliki satu atau lebih jadwal rapat dalam satu bulan dengan hari dan jam tertentu.
- Waktu mulai dan selesai rapat: Setiap rapat memiliki waktu tersendiri yang sudah jelas dan tidak boleh bertabrakan dengan rapat lain di hari yang sama.
- Ruang rapat: Terbatas, hanya ada satu ruang rapat yang tersedia.
- Tujuan optimasi: Memaksimalkan jumlah rapat yang dapat diselenggarakan tanpa ada yang bertabrakan sehingga penggunaan ruang rapat lebih efisien.

Pada kasus ini terdapat 50 jadwal rapat, _S = {rapat1,rapat2,rapat3,...,rapat50}_ yang akan menggunakan suatu ruang rapat dimana hanya dapat digunakan untuk satu rapat saja di waktu tertentu.
Setiap rapat _i_ memiliki waktu mulai _s i_ dan waktu selesai _f i_ , dimana _s i_ &le; _f i_ . Dua aktifitas _i_ dan _j_ dikatakan **kompatibel** jika interval [_s i_ , _f i_] dan [_s j_ , _f j_] tidak beririsan/bertabrakan.

## Pendekatan Algoritma Greedy
Algoritma greedy digunakan pada kasus ini karena mudah dipahami dan diimplemetasikan. Pada setiap langkahnya dipilih solusi lokal yang terbaik (memilih rapat dengan waktu selesai terawal). Dalam permasalahan pemilihan kegiatan seperti penjadwalan, solusi lokal tersebut akan membantu mencapai solusi keseluruhan yang cukup optimal, yaitu memaksimalkan jumlah rapat tanpa bertabrakan. 

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

## Batasan
- Pada program ini tidak memperhitungkan kemungkinan penjadwalan ulang rapat yang tidak terselenggara karena bertabrakan dengan rapat lain.
- Pendekatan algoritma greedy berdasarkan waktu selesai rapat dan tidak mempertimbangkan prioritas komite dan topiknya.

## Credit
Ismi Nurul Na'imah  
(24/541118/PPA/06824)
