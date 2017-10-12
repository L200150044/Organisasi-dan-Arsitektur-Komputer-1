<p align="center">
<b>Organisasi dan Arsitektur Komputer</b><br/>
<b>Set Instruksi Intel x86</b>
</p><br/><br/>

## x86

<b>x86</b> atau <b>80x86</b> adalah nama umum dari arsitektur mikroprosesor yang pertama kali dikembangkan dan diproduksi oleh Intel. Arsitektur <b>x86</b> saat ini mendominasi komputer desktop, komputer portabel, dan pasar server sederhana.<br>

### Keping Mikroposesor Intel Pentium 4; Seri Northwood

Arsitektur ini dikenal dengan nama x86 karena prosesor-prosesor awal dari keluarga arsitektur ini memiliki nomor model yang diakhiri dengan urutan angka "86": prosesor 8086, 80186, 80286, 386, dan 486. Karena nomor tidak bisa dijadikan merek dagang, Intel akhirnya menggunakan kata Pentium untuk merek dagang processor generasi kelima mereka.
Arsitektur ini telah dua kali diperluas untuk mengakomodasi ukuran word yang lebih besar. Pada tahun 1985, Intel mengumumkan rancangan generasi 386 32-bit yang menggantikan rancangan generasi 286 16-bit. Arsitektur 32-bit ini dikenal dengan nama x86-32 atau IA-32 (singkatan dari Intel Architecture, 32-bit). Kemudian pada tahun 2003, AMD memperkenalkan Athlon 64, yang menerapkan secara lebih jauh pengembangan dari arsitektur ini menuju ke arsitektur 64-bit, dikenal dengan beberapa istilah x86-64, AMD64 (AMD), EM64T atau IA-32e (Intel), dan x64 (Microsoft).

### Jenis x86 data

x86 dapat menangani jenis data 8 (byte), 16 (kata), 32 (doubleword), 64 (quadword), dan 128 (double quadword) bit panjangnya. Untuk memungkinkan fleksibilitas maksimum dalam struktur data dan pemanfaatan memori efisien, kata tidak perlu selaras pada evennumbered alamat; doublewords tidak perlu selaras pada alamat merata dibagi jadi 4; dan quadwords tidak perlu selaras pada alamat dibagi secara merata 8; dan sebagainya.

### Rancangan

Arsitektur x86 adalah rancangan Set Instruksi Komputer Kompleks (Complex Instruction Set Computer) dengan panjang instruksi yang bervariasi. Word disimpan dengan urutan endian-kecil. Kompatibilitas mundur menjadi motivasi terkuat dalam pengembangan arsitektur x86 (keputusan ini menjadi sangat penting dan sering dikritik, terutama oleh pesaing dari pendukung arsitektur prosesor lainnya, yang dibuat frustasi oleh sukses yang berkelanjutan dari arsitektur ini yang secara umum dipandang memilki banyak kelemahan). Prosesor-prosesor terkini dari x86 menerapkan beberapa langkah penerjemah (dekoder) "tambahan" untuk (saat eksekusi) memecah (sebagian besar) instruksi x86 kedalam potongan-potongan kecil instruksi (dikenal dengan "micro-ops") yang selanjutnya dieksekusi oleh arsitektur setara dengan arsitektur RISC.

Mikroprosesor x86 dapat bekerja dalam beberapa modus berikut:

- [Real-mode](#real-mode) (Modus Real)
- [Protected Mode](#protected-mode) (Modus terproteksi)
- [Virtual Protected Mode](#virtual-protected-mode) (Modus Terproteksi Virtual)
- [Compatibility Mode](#ia32eamd64x64x86-64-compatibility-mode)
- [Long Mode/IA32e Full Mode](#ia32ex86-64amd64x64em64t-long-mode)

#### Real-Mode
Real-Mode adalah sebuah modus di mana prosesor Intel x86 berjalan seolah-olah dirinya adalah sebuah prosesor Intel 8086 atau Intel 8088, meski ia merupakan prosesor Intel 80286 atau lebih tinggi. Karenanya, modus ini juga disebut sebagai modus 8086 (8086 Mode). Dalam modus ini, prosesor hanya dapat mengeksekusi instruksi 16-bit saja dengan menggunakan register internal yang berukuran 16-bit, serta hanya dapat mengakses hanya 1024 KB dari memori karena hanya menggunakan 20-bit jalur bus alamat. Semua program DOS berjalan pada modus ini.

Prosesor yang dirilis setelah 8086, semacam Intel 80286 juga dapat menjalankan instruksi 16-bit, tapi jauh lebih cepat dibandingkan 8086. Dengan kata lain, Intel 80286 benar-benar kompatibel dengan prosesor Intel 8086 yang didesain sebelumnya. Sehingga prosesor Intel 80286 pun dapat menjalankan program-program 16-bit yang didesain untuk 8086 (IBM PC), dengan tentunya kecepatan yang jauh lebih tinggi.

Dalam Real-mode, tidak ada proteksi ruang alamat memori, sehingga tidak dapat melakukan multi-tasking. Inilah sebabnya, mengapa program-program DOS bersifat single-tasking. Jika dalam modus real terdapat multi-tasking, maka kemungkinan besar antara dua program yang sedang berjalan, terjadi tabrakan (crash) antara satu dengan lainnya.

#### Protected Mode

Modus terproteksi (protected mode) adalah sebuah modus di mana terdapat proteksi ruang alamat memori yang ditawarkan oleh mikroprosesor untuk digunakan oleh sistem operasi. Modus ini datang dengan mikroprosesorIntel 80286 atau yang lebih tinggi. Karena memiliki proteksi ruang alamat memori, maka dalam modus ini sistem operasi dapat melakukan multitasking.

Prosesor Intel 80286 memang dilengkapi kemampuan masuk ke dalam modus terproteksi, tapi tidak dapat keluar dari modus tersebut tanpa harus mengalami reset (warm boot atau cold boot). Kesalahan ini telah diperbaiki oleh Intel dengan merilis prosesor Intel 80386 yang dapat masuk ke dalam modus terproteksi dan keluar darinya tanpa harus melakukan reset. Inilah sebabnya mengapa Windows 95/Windows 98 dilengkapi dengan modus Restart in MS-DOS Mode, meski sebenarnya sistem operasi tersebut merupakan sistem operasi yang berjalan dalam modus terproteksi.

#### Virtual Protected Mode

Virtual Protected Mode juga kadang disebut sebagai Virtual Real Mode. Dalam modus ini, sebuah prosesor Intel x86 berjalan dalam modus terproteksi tetapi mengizinkan aplikasi-aplikasi 16-bit real-mode agar dapat dijalankan di atas sistem operasi. Microsoft Windows 3.1, yang berjalan di dalam modus Enhanced 386, Windows 95, serta Windows 98 mendukung modus ini sepenuhnya. Sistem-sistem operasi dapat menjalankan beberapa aplikasi 16-bit real-mode secara sekaligus, pada window MS-DOS Prompt yang berbeda-beda, karena memang Microsoft mengimplementasikan sebuah lapisan emulasi yang disebut sebagai DOS Protected Mode Interface (DPMI). Setiap window MS-DOS Prompt yang dibuat, aplikasi hanya berjalan dalam real mode, tapi karena Windows 3.1 (yang berjalan dalam modus Enhanced 386) dan Windows 95/98 berjalan dalam modus terproteksi, aplikasi akan menganggap dirinya berjalan pada komputer yang berbeda, meski pada fisiknya mereka dijalankan pada modus yang sama. Hal ini mengizinkan aplikasi-aplikasi 16-bit real-mode agar dapat dijalankan secara serentak (multitasking), meski pada awalnya aplikasi 16-bit berjalan dalam kondisi single-tasking.

DPMI digunakan oleh Windows 3.1 ke atas untuk mengakses extended memory agar dapat digunakan oleh aplikasi Windows. DPMI mengizinkan program-program dapat menggunakan memori yang lebih banyak, meski pada aslinya program tersebut merupakan program 16-bit. Hal ini populer dilakukan, khususnya bagi program-program game komputer DOS, karena game-game tersebut dapat mengakses lebih dari 1 MB (diberi hak akses oleh sistem operasi). DPMI dapat melakukan switching prosesor dari real-mode ke protected mode atau sebaliknya.

#### IA32e/AMD64/x64/x86-64 Compatibility Mode

Modus kompatibilitas adalah sebuah modus prosesor berbasis IA32e (x86-64, AMD64, EM64T, atau x64) di mana prosesor sedang menjalankan instruksi 32-bit (sistem operasi 32-bit dan aplikasinya yang dijalankan di atas prosesor x64 atau sistem operasi 64-bit yang menjalankan aplikasi 32-bit). Dalam modus ini, prosesor tersebut bekerja seolah-olah dirinya adalah prosesor x86 32-bit, sehingga hanya dapat mengalamati memori hingga 4 GB saja.

#### IA32e/x86-64/AMD64/x64/EM64T Long Mode

Modus panjang (long mode) adalah sebuah modus prosesor 64-bit IA32e (x86-64/AMD64/x64/EM64T) yang berjalan di atas sistem operasi 64-bit, sehingga ia dapat mengeluarkan seluruh kemampuannya, seperti halnya mengakses memori lebih besar daripada 4 GB (hingga batasan yang dimiliki oleh prosesor dan sistem operasi), dan menjalankan aplikasi 64-bit. Hanya beberapa sistem operasi yang dapat menjalankan prosesor IA32e dalam modus ini, yakni Windows XP Professional x64 Edition, Windows Server 2003, GNU/Linux (versi kernel2.6 ke atas), Solaris 10 dan beberapa varian UNIX lainnya.

