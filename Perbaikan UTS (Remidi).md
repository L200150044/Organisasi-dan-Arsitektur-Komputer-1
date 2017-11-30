# Ujian Tengah Semester Ganjil 2017/2018

- Nama : Abdul Kemal Nasa'i Wibowo
- NIM  : L200150043

## Soal :
1.	Sejarah komputer, (a) Siapakah yang memulai membuat komputer? (2%) (b) kapan mulainya seleai setelah berapa tahun? (3%) (c) Apa nama universitasnya? (5%)
2.	Apa perubahan yang diciptakan oleh Von Numman dalam dunia komputer? (10%)
3.	Apa yang dimaksud program dalam komputer? (10%)
4.	Sebutkan beberapa register utama dalam sebuah processor dan jelaskan fungsinya (10%)
5.	Gambarkan blok rangkaian dasar komputer dan terangkan proses komputer dalam mengeksekusi program! (instruction cycle) (10%)
6.	Sebutkan empat proses utama yang mungkin terjadi ketika komputer menjalankan kode program (instruction set)! (10%)
7.	Jelaskan cara kerja keyboard! (jelaskan proses pengolahan data mulai dari user menekan tombol sampai huruf ditampilkan di layar) (10%)
8.	Apa fungsi cache dalam komputer (10%)
9.	Gambarkan posisi cache (l1, L2, L3) dalam komputer dan jelaskan cara kerjanya! (10%)
10.	Apa perbedaan antara Static dan dinamik RAM, berikan contoh penggunaan dari masing-masing jenis memory tersebut (10%).

## Penyelesaian :
1.	Sejarah komputer, (a) Siapakah yang memulai membuat komputer? (2%) (b) kapan mulainya seleai setelah berapa tahun? (3%) (c) Apa nama universitasnya? (5%)
    
    a.   Prof. Mauchly dan Muridnya Ecket
    
    b.   Dimulai pada tahun 1943 selesai 1946
    
    c.   University of Pennsylvania
   
2.	Apa perubahan yang diciptakan oleh Von Numman dalam dunia komputer? (10%)
    -   Adanya ide untuk menyimpan program (memory)
    -   Memory digunakan untuk PROGRAM (aplikasi)  dan DATA
    -   ALU (Aritmatik Logic Unit / Processor) bekerja dengan angka BINARY
    -   Ada bagian unit KONTROL untuk mengatur kode program yang akan dieksekusi
    -   Ada unit Input/Output yang dikendalikan oleh unit KONTROL
    -   Dibuat di Princeton Institute for Advance Studies (IAS)
    -   Selesai tahun 1952
3.	Apa yang dimaksud program dalam komputer? (10%).
    -   Teridiri atas urutan langkah
    -   Pada setiap langkah dilakukan operasi aritmatik atau logik.
    -   Pada setiap operasi diperlukan sinyal kontrol yang berbeda.
4.	Sebutkan beberapa register utama dalam sebuah processor dan jelaskan fungsinya (10%)
    -   Control Unit : untuk memberikan arahan/kendali/ kontrol terhadap operasi yang dilakukan di bagian ALU (Arithmetic Logical Unit) di dalam CPU tersebut.
    -   ALU : untuk melakukan operasi hitungan aritmatika dan logika.
5.	Gambarkan blok rangkaian dasar komputer dan terangkan proses komputer dalam mengeksekusi program! (instruction cycle) (10%)


![diagram blok PC](https://raw.githubusercontent.com/L200150043/Organisasi-dan-Arsitektur-Komputer/master/img/UTS-nomor-5.png)

Instruction Cycle:
Fetch Cycle : membaca/memindahkan kode program/data dari memori ke CPU (IR/MBR)
Execute Cycle: Menjalankan operasi sesuai kode yang diperoleh dalam ALU unit. 
 
Note: Pembacaan kode/data bergantung kepada isi dari memory yang alamatnya ditunjuk oleh PC (Program Counter)
 
 
  - FETCH Cycle:
    -   PC (Program Counter) berisi alamat dari intruksi berikutnya yang akan di baca berikutnya.
    -   Processor membaca instruksi dari lokasi memory yang ditunjuk oleh PC.
    -   Increment PC ( menambah alamat dalam PC dengan angka satu)
    -   Instruksi (kode program) akan dipindahkan ke IR (Intruction Register)
    -   Processor menterjemahkan kode program dan melakukan aksi yang diperlukan (sesuai kode yang diberikan)
 
  - Execute Cycle:
    -   PROCESSOR-MEMORY: Perpindahan data antara CPU dan MAIN MEMORY.
    -   Processor - I/O :  Perpindahan data antara CPU dan I/O
    -   DATA processing: melakukan operasi ARITMATIK atau LOGIK pada data
    -   CONTROL: Menentukan operasi berikutnya, dapat berasal dari alamat memeory berikutnya atau melompat ke alamat memory tertentu (JUMP)
    -   Dapat berupa kombinasi dari proses di atas.
    
6.	Sebutkan empat proses utama yang mungkin terjadi ketika komputer menjalankan kode program (instruction set)! (10%)
    -   Proses memulai
    -   Fetch instruksi selanjutnya
    -   Execute instruksi
    -   Berhenti
7.	Jelaskan cara kerja keyboard! (jelaskan proses pengolahan data mulai dari user menekan tombol sampai huruf ditampilkan di layar) (10%)

    keyboard komputer bekerja pada saat kita menekan tombol kemudian di bawah tombol tersebut terdapat chip yang akan mentransmisikan sinyal kepada unit proses komputer, sinyal yang di transmisikan berbentuk kode biner dan kode biner tersebut akan di proses oleh unit proses komputer kemudian kode biner tersebut di tampilkan pada unit output monitor menjadi tampilan asli yang berbentuk huruf, angka atau perintah untuk menjalankan sebuah program komputer.
    

8.	Apa fungsi cache dalam komputer (10%)
    
    Cache berfungsi sebagai tempat penyimpanan sementara untuk data atau instruksi yang diperlukan oleh processor. Secara mudahnya, cache berfungsi untuk mempercepat akses data pada komputer karena cache menyimpan data/informasi yang telah diakses oleh suatu buffer, sehingga meringankan kerja processor.
    
9.	Gambarkan posisi cache (l1, L2, L3) dalam komputer dan jelaskan cara kerjanya! (10%)


![chace](https://raw.githubusercontent.com/L200150043/Organisasi-dan-Arsitektur-Komputer/master/img/UTS-nomor-9.png)

  - CPU meminta data/instruksi dari lokasi memory (main Memory)
  - Memeriksa apakah data/instruksi sudah ada di dalam  CACHE (biasanya dilakukan secara hardware)
  - Jika data/instruksi sudah ada dalam cache ambil dari cache. (lebih cepat)
  - Jika belum ada di dalam cache, membaca blok memory (terkecil 4 byte) untuk dipindahkan  ke dalam cache.
  - Kirimkan data/instruksi dari cache ke CPU
  - Cahce akan menyimpan data tambahan berupa tags untuk identifikasi lokasi blok memory.

10.	Apa perbedaan antara Static dan dinamik RAM, berikan contoh penggunaan dari masing-masing jenis memory tersebut (10%).
    
  - RAM STATIS
    -   Data disimpan sebagai SWITCH ON/OFF (komponen berupa transistor)
    -   Ukuran fisik relatif lebih besar, setiap bit data diperlukan paling sedikit 6 transistor.
    -   Lebih mahal 
    -   Kapasitas memori lebih kecil 
    -   Kecepatan akses (baca &tulis) lebih cepat 
    -   Tidak perlu sinyal REFRESH.
    -   Aplikasi: digunakan untuk CACHE MEMORY 

  - RAM DINAMIS 
    -   Data disimpan sebagai MUATAN DALAM KAPASITOR  (komponen berupa kapasitor)
    -   Ukuran fisik lebih kecil untuk setiap bit data, sebbab komponen lebih sedikit (1 bit terdiri atas 1 transistor + 1 kapasitor)
    -   Lebih murah 
    -   Kapasitas memori lebih tinggi 
    -   Kecepatan akses (baca & tulis) lebih rendah dibanding statis
    -   Memerlukan sinyal REFRESH (untuk mempertahankan data) meskipun ada catu daya, sehingga rangfkaian menjadi lebih rumit.
    -   Banyak digunakan untuk RAM pada sistem komputer saat ini contoh SDRAM dan DDRAM (Double Data Rate RAM)
