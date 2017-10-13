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



<table width="98%" cellpadding="1" cellspacing="0">
	<col width="34*">
	<col width="34*">
	<col width="61*">
	<col width="53*">
	<col width="74*">
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p align="center"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>Generation</b></font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p align="center"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>First
			introduced</b></font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p align="center"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>Prominent
			consumer CPU brands</b></font></font></p>
		</td>
		<td width="21%" style="border: none; padding: 0in">
			<p align="center"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>Linear/physical
			address space</b></font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p align="center"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>Notable
			(new) features</b></font></font></p>
		</td>
	</tr>
	<tr>
		<td rowspan="2" width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1978</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Intel
			8086, Intel 8088 and clones</font></font></p>
		</td>
		<td rowspan="2" width="21%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>16-bit</b></font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">
			/ 20-bit (segmented)</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">First
			x86 microprocessors</font></font></p>
		</td>
	</tr>
	<tr>
		<td rowspan="2" width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1982</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Intel
			80186, Intel 80188 and clones, NEC V20/V30</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Hardware
			for fast address calculations, fast mul/div, etc.</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Intel
			80286 and clones</font></font></p>
		</td>
		<td width="21%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>16-bit</b></font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">
			(30-bit virtual) / 24-bit (segmented)</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">MMU,
			for protected mode and a larger address space.</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">3
			(IA-32)</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1985</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Intel
			80386 and clones, AMD Am386</font></font></p>
		</td>
		<td rowspan="5" width="21%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>32-bit</b></font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">
			(46-bit virtual) / 32-bit</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">32-bit
			instruction set, MMU with paging.</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">4
			(FPU)</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1989</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Intel486
			and clones, AMD Am486/Am5x86</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">RISC-like
			pipelining, integrated x87 FPU (80-bit), on-chip cache.</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">4/5</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1997</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">IDT/Centaur-C6,
			Cyrix III-Samuel, VIA C3-Samuel2 / VIA C3-Ezra (2001), VIA C7
			(2005)</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">In-order,
			integrated FPU, some models with on-chip L2 cache, MMX, SSE.</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">5</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1993</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Pentium,
			Pentium MMX, Cyrix 5x86, Rise mP6</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Superscalar,
			64-bit databus, faster FPU, MMX (2</font></font><font face="Tahoma, serif"><font size="3" style="font-size: 12pt">�</font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">-
			32-bit).</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">5/6</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1996</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">AMD
			K5, Nx586 (1994)</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">μ-op
			translation.</font></font></p>
		</td>
	</tr>
	<tr>
		<td rowspan="3" width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">6</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1995</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Pentium
			Pro, Cyrix 6x86, Cyrix MII, Cyrix III-Joshua (2000)</font></font></p>
		</td>
		<td rowspan="6" width="21%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><i>As
			above</i></font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">
			/ </font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>36</b></font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">-bit
			physical (PAE)</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">μ-op
			translation, conditional move instructions, Out-of-order, register
			renaming, speculative execution, PAE (Pentium Pro), in-package L2
			cache (Pentium Pro).</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1997</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">AMD
			K6/-2/3, Pentium II/III</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">L3-cache
			support, 3DNow!, SSE (2</font></font><font face="Tahoma, serif"><font size="3" style="font-size: 12pt">�</font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">-
			64-bit).</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2003</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Pentium
			M, Intel Core (2006)</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">optimized
			for low power.</font></font></p>
		</td>
	</tr>
	<tr>
		<td rowspan="2" width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">7</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1999</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Athlon,
			Athlon XP</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Superscalar
			FPU, wide design (up to three x86 instr./clock).</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2000</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Pentium
			4</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">deeply
			pipelined, high frequency, SSE2, hyper-threading.</font></font></p>
		</td>
	</tr>
	<tr>
		<td rowspan="4" width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">7/8</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2000</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Transmeta
			Crusoe, Efficeon</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">VLIW
			design with x86 emulator, on-die memory controller.</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2004</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Pentium
			4 Prescott</font></font></p>
		</td>
		<td rowspan="4" width="21%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>64-bit</b></font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">
			/ 40-bit physical in first AMD implementation</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Very
			deeply pipelined, very high frequency, SSE3, 64-bit capability
			(integer CPU) is available only in LGA 775 sockets.</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2006</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Intel
			Core 2</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">64-bit
			(integer CPU), low power, multi-core, lower clock frequency, SSE4
			(Penryn).</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2008</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">VIA
			Nano</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Out-of-order,
			superscalar, 64-bit (integer CPU), hardware-based encryption, very
			low power, adaptive power management.</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">8
			(x86-64)</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2003</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Athlon
			64, Opteron</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">x86-64
			instruction set (CPU main integer core), on-die memory controller,
			hypertransport.</font></font></p>
		</td>
	</tr>
	<tr>
		<td rowspan="4" width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">8/9</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2007</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">AMD
			Phenom</font></font></p>
		</td>
		<td rowspan="4" width="21%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><i>As
			above</i></font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">
			/ 48-bit physical for AMD Phenom</font></font></p>
		</td>
		<td rowspan="2" width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Monolithic
			quad-core, SSE4a, HyperTransport 3 or QuickPath, native memory
			controller, on-die L3 cache, modular.</font></font></p>
		</td>
	</tr>
	<tr>
		<td rowspan="2" width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2008</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Intel
			Core i3/i5/i7, AMD Phenom II</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Intel
			Atom</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">In-order
			but highly pipelined, very-low-power, on some models: 64-bit
			(integer CPU), on-die GPU.</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2011</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">AMD
			Bobcat, Llano</font></font></p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Out-of-order,
			64-bit (integer CPU), on-die GPU, low power (Bobcat).</font></font></p>
		</td>
	</tr>
	<tr>
		<td rowspan="2" width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">9
			(GPU)</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2011</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Intel
			Sandy Bridge/Ivy Bridge, AMD Bulldozer and Trinity</font></font></p>
		</td>
		<td width="21%" style="border: none; padding: 0in">
			<p>&nbsp;</p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">SSE5/AVX
			(4</font></font><font face="Tahoma, serif"><font size="3" style="font-size: 12pt">�</font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">-
			64-bit), highly modular design, integrated on-die GPU.</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2013</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Intel
			Haswell</font></font></p>
		</td>
		<td width="21%" style="border: none; padding: 0in">
			<p>&nbsp;</p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">AVX2
			and FMA3 instructions.</font></font></p>
		</td>
	</tr>
	<tr>
		<td width="13%" style="border: none; padding: 0in">
			<p>—<font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><br/>
(MIC
			pilot)</font></font></p>
		</td>
		<td width="13%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2012</font></font></p>
		</td>
		<td width="24%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Intel
			Xeon Phi (Larrabee)</font></font></p>
		</td>
		<td width="21%" style="border: none; padding: 0in">
			<p>&nbsp;</p>
		</td>
		<td width="29%" style="border: none; padding: 0in">
			<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Many
			Integrated Cores (62), In-order P54C with x86-64, Very wide vector
			unit, LRBni instructions (8</font></font><font face="Tahoma, serif"><font size="3" style="font-size: 12pt">�</font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">-
			64-bit)</font></font></p>
		</td>
	</tr>
</table>

<br>

<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>Set
intruksi 8051 dibagi menjadi 3 kelompok besar, yaitu :</b></font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1.
Intruksi-intruksi transfer data</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2.
Intruksi-intruksi pemrosesan data</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">3.
Intruksi-intruksi lompatan</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>1.
Intruksi-intruksi transfer data</b></font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1.1.
Daftar Intruksi Transfer data</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%">

![table](https://raw.githubusercontent.com/L200150043/Organisasi-dan-Arsitektur-Komputer/master/img/tugas01-table.jpg)

&nbsp;</p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><br/>

</p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1.2.
Instruksi Transfer Data</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">a)
RAM Internal</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Perintah
perpindahan data (MOV, XCH, POP, PUSH) pada RAM internal membutuhkan
1 sampai 2 cycle. Format instruksi :</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">MOV
(tujuan), (asal)</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Memungkinkan
data untuk berpindah diantara 2 lokasi RAM internal atau SFR tanpa
harus melalui akumulator terlebih dahulu.</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">b)
RAM EKternal</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Perintah
MOV 16-bit digunakan untuk inisialisasi DPTR atau untuk akses data
16-bit pada memori ekternal.perpindahan data antera memori internal
dan ekternal menggunakan indirect addressing dengan menggunakan
alamat 1-byte (@R1) atau 2-byte (@DPTR).</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">c)
Look Up Tables</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Ada
dua perintah untuk membaca look-up tables pada ROM. MOVC (move
constant) menggunakan program counter sebagai base register dan
akumulator sebagai offsetnya.</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">MOVC
A, @A+DPTR</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Perintah
tersebut dapat mengakses 256 entri. Nomor entri dimasukkan ke
akumulator dan awal tabelnya pada DPTR.</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">MOVC
A, @A+PC</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>2.
Instruksi-intruksi Pemrosesan Data</b></font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Instruksi-intruksi
pemrosesan data dibagi manjadi 2 :</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">1.
Instruksi-intruksi Logika</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">2.
Intruksi-intruksi Aritmatika</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Set
intruksi Aritmatika terdiri dari :</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">-
Instruksi-instruksi penjumlahan dan pengurangan</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">-
Instruksi-instruksi perkalian dan pembagian</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">-
Instruksi-instruksi Increment dan Decrement</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">-
Instruksi pengubahan ke decimal (Decimal Adjust)</font></font></p>
<p align="justify" style="margin-bottom: 0in; line-height: 150%"><br/>

</p>
<table width="98%" cellpadding="1" cellspacing="0">
	<col width="42*">
	<col width="97*">
	<col width="93*">
	<col width="24*">
	<thead>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p align="center"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>Instruction</b></font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p align="center"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>Meaning</b></font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p align="center"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>Notes</b></font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p align="center"><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><b>Opcode</b></font></font></p>
			</td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">AAA</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">ASCII
				adjust AL after addition</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">used
				with unpacked binary coded decimal</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">AAD</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">ASCII
				adjust AX before division</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">8086/8088
				datasheet documents only base 10 version of the AAD instruction
				(opcode 0xD5 0x0A), but any other base will work. Later Intel's
				documentation has the generic form too. NEC V20 and V30 (and
				possibly other NEC V-series CPUs) always use base 10, and ignore
				the argument, causing a number of incompatibilities</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">AAM</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">ASCII
				adjust AX after multiplication</font></font></p>
			</td>
			<td rowspan="2" width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Only
				base 10 version is documented, see notes for AAD</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">AAS</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">ASCII
				adjust AL after subtraction</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">ADC</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Add
				with carry</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">destination&nbsp;:=
				destination + source + carry_flag</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">ADD</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Add</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(1)
				r/m += r/imm; (2) r += m/imm;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">AND</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Logical
				AND</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(1)
				r/m &amp;= r/imm; (2) r &amp;= m/imm;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CALL</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Call
				procedure</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">push
				eip + 2&nbsp;; jmp operand</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CBW</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Convert
				byte to word</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CLC</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Clear
				carry flag</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CF
				= 0;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CLD</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Clear
				direction flag</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">DF
				= 0;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CLI</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Clear
				interrupt flag</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">IF
				= 0;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CMC</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Complement
				carry flag</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CMP</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Compare
				operands</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CMPSB</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Compare
				bytes in memory</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CMPSW</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Compare
				words</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CWD</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Convert
				word to doubleword</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">DAA</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Decimal
				adjust AL after addition</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(used
				with packed binary coded decimal)</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">DAS</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Decimal
				adjust AL after subtraction</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">DEC</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Decrement
				by 1</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">DIV</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Unsigned
				divide</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">DX:AX
				= DX:AX / r/m; resulting DX = remainder</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">ESC</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Used
				with floating-point unit</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">HLT</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Enter
				halt state</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">0xF4</font></font></p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">IDIV</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Signed
				divide</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">DX:AX
				= DX:AX / r/m; resulting DX = remainder</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">IMUL</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Signed
				multiply</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(1)
				DX:AX = AX * r/m; (2) AX = AL * r/m</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">IN</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Input
				from port</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(1)
				AL = port[imm]; (2) AL = port[DX]; (3) AX = port[DX];</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">INC</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Increment
				by 1</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">INT</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Call
				to interrupt</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">INTO</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Call
				to interrupt if overflow</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">IRET</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Return
				from interrupt</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Jcc</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Jump
				if condition</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(</font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><i>JA,
				JAE, JB, JBE, JC, JCXZ, JE, JG, JGE, JL, JLE, JNA, JNAE, JNB,
				JNBE, JNC, JNE, JNG, JNGE, JNL, JNLE, JNO, JNP, JNS, JNZ, JO, JP,
				JPE, JPO, JS, JZ</i></font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">)</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">JMP</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Jump</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">LAHF</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Load
				flags into AH register</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">LDS</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Load
				pointer using DS</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">LEA</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Load
				Effective Address</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">LES</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Load
				ES with pointer</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">LOCK</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Assert
				BUS LOCK# signal</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(for
				multiprocessing)</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">LODSB</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Load
				string byte</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">if
				(DF==0) AL = *SI++; else AL = *SI--;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">LODSW</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Load
				string word</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">if
				(DF==0) AX = *SI++; else AX = *SI--;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">LOOP/LOOPx</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Loop
				control</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(</font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><i>LOOPE,
				LOOPNE, LOOPNZ, LOOPZ</i></font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">)
				if (x &amp;&amp; --CX) goto lbl;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">MOV</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Move</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">copies
				data from one location to another, (1) r/m = r; (2) r = r/m;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">MOVSB</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Move
				byte from string to string</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">if
				(DF==0) *(byte*)DI++ = *(byte*)SI++; else *(byte*)DI-- =
				*(byte*)SI--;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">MOVSW</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Move
				word from string to string</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">if
				(DF==0) *(word*)DI++ = *(word*)SI++; else *(word*)DI-- =
				*(word*)SI--;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">MUL</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Unsigned
				multiply</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(1)
				DX:AX = AX * r/m; (2) AX = AL * r/m;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">NEG</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Two's
				complement negation</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">r/m
				*= -1;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">NOP</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">No
				operation</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">opcode
				equivalent to XCHG EAX, EAX</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">NOT</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Negate
				the operand, logical NOT</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">r/m
				^= -1;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">OR</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Logical
				OR</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">=
				r/imm; (2) r |= m/imm;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">OUT</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Output
				to port</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(1)
				port[imm] = AL; (2) port[DX] = AL; (3) port[DX] = AX;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">POP</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Pop
				data from stack</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">*SP++
				= r/m; POP CS (opcode 0x0F) works only on 8086/8088. Later CPUs
				use 0x0F as a prefix for newer instructions.</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">0x0F</font></font></p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">POPF</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Pop
				data from flags register</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">*SP++
				= flags;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">PUSH</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Push
				data onto stack</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">*--SP
				= r/m;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">PUSHF</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Push
				flags onto stack</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">*--SP
				= flags;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">RCL</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Rotate
				left (with carry)</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">RCR</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Rotate
				right (with carry)</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">REPxx</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Repeat
				MOVS/STOS/CMPS/LODS/SCAS</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(</font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt"><i>REP,
				REPE, REPNE, REPNZ, REPZ</i></font></font><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">)</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">RET</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Return
				from procedure</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">either
				RETN or RETF depending on memory model of assembler etc.</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">RETN</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Return
				from near procedure</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">RETF</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Return
				from far procedure</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">ROL</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Rotate
				left</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">ROR</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Rotate
				right</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">SAHF</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Store
				AH into flags</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">SAL</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Shift
				Arithmetically left (signed shift left)</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(1)
				r/m &lt;&lt;= 1; (2) r/m &lt;&lt;= CL;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">SAR</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Shift
				Arithmetically right (signed shift right)</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(1)
				(signed)r/m &gt;&gt;= 1; (2) (signed)r/m &gt;&gt;= CL;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">SBB</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Subtraction
				with borrow</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">alternative
				1-byte encoding of SBB&nbsp;AL,&nbsp;AL is available via
				undocumented SALC instruction</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">SCASB</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Compare
				byte string</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">SCASW</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Compare
				word string</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">SHL</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Shift
				left (unsigned shift left)</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">SHR</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Shift
				right (unsigned shift right)</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">STC</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Set
				carry flag</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">CF
				= 1;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">STD</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Set
				direction flag</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">DF
				= 1;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">STI</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Set
				interrupt flag</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">IF
				= 1;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">STOSB</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Store
				byte in string</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">if
				(DF==0) *ES:DI++ = AL; else *ES:DI-- = AL;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">STOSW</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Store
				word in string</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">if
				(DF==0) *ES:DI++ = AX; else *ES:DI-- = AX;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">SUB</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Subtraction</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(1)
				r/m -= r/imm; (2) r -= m/imm;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">TEST</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Logical
				compare (AND)</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(1)
				r/m &amp; r/imm; (2) r &amp; m/imm;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">WAIT</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Wait
				until not busy</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Waits
				until BUSY# pin is inactive (used with floating-point unit)</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">XCHG</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Exchange
				data</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">r&nbsp;:=:
				r/m;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">XLAT</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Table
				look-up translation</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">behaves
				like </font></font><font face="Courier New, serif"><font size="2" style="font-size: 10pt">MOV
				AL, [BX+AL]</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td width="16%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">XOR</font></font></p>
			</td>
			<td width="38%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">Exclusive
				OR</font></font></p>
			</td>
			<td width="36%" style="border: none; padding: 0in">
				<p><font face="Times New Roman, serif"><font size="3" style="font-size: 12pt">(1)
				r/m ^= r/imm; (2) r ^= m/imm;</font></font></p>
			</td>
			<td width="9%" style="border: none; padding: 0in">
				<p lang="id-ID"><br/>

				</p>
			</td>
		</tr>
	</tbody>
</table>
