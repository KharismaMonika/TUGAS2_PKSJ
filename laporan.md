# LAPORAN TUGAS 1 SQL INJECTION
 OLEH 
- 5114100092    KHARISMA MONIKA
- 5114100131    Michael Dave
- 5114100081    M. Luqmanul Hakim

___

## PENDAHULUAN
### LATAR BELAKANG
SQL Injection merupakan sebuah topik yang sedang hangat diperbincangkan diera perkembangan teknologi saat ini. Hal ini dikarenakan dengan metode ini kita bisa mengetahui informasi penting didalam sebuah sistem yang seharusnya tidak boleh kita ketahui. Untuk mengetahui cara kerja dari sql injection, kami mencoba melakukan simulasi sql injection pada wordpress dengan menggunakan ubuntu.
### TUJUAN
Memenuhi Tugas 2 dari Mata Kuliah Perancangan Keamanan Sistem dan Jaringan
### MANFAAT
Mengetahui cara kerja SQL Injection dan cara untuk mencegahnya
___

## DASAR TEORI
* ### Ubuntu Server
Ubuntu server adalah ubuntu yang didesain untuk di install di server. Perbedaan mendasar, di Ubuntu Server tidak tersedia GUI. Jika anda menggunakan ubuntu server artinya anda harus bekerja dengan perintah perintah di layar hitam yang sering disebut konsole. Jika anda datang dari windows, maka tampilan ubuntu server seperti DOS. Bagi orang awam pemakai desktop, jelas tidak ada manfaatnya, tapi bagi admin jaringan, warnet, kantor, server dan perusahaan webhosting, ubuntu server merupakan solusi mudah dan free untuk membangun layanan seperti file sharing , printer sharing atau webhosting. 

Ubuntu server walaupun hanya menggunakan CLI (Coomand line interface) tidaklah sesusah yang dikira karena sudah banyak tutorial dan help bawaan dari perintah itu sendiri. Yang dibutuhkan adalah kemauan membaca manual dan belajar bahasa inggris.

* ### Ubuntu Dekstop
Ubuntu dekstop adalah sistem operasi ubuntu dengan GUI (Graphic User Interface)

* ### Kali Linux
Kali Linux adalah keluarga sistem Debian yang didesign untuk digital forensik dan testing penetrasi sistem. Banyak dari package pada Kali Linux dikembangkan dari repositori Debian. Kali Linux juga memiliki project untuk dikembangkan pada perangkat Android bernama Kali Linux NetHunter. 

* ### SQL Injection
Injeksi SQL (Bahasa Inggris: SQL Injection)adalah sebuah teknik yang menyalahgunakan sebuah celah keamanan yang terjadi dalam lapisan basis data sebuah aplikasi. Celah ini terjadi ketika masukan pengguna tidak disaring secara benar dari karakter-karakter pelolos bentukan string yang diimbuhkan dalam pernyataan SQL atau masukan pengguna tidak bertipe kuat dan karenanya dijalankan tidak sesuai harapan. Ini sebenarnya adalah sebuah contoh dari sebuah kategori celah keamanan yang lebih umum yang dapat terjadi setiap kali sebuah bahasa pemrograman atau skrip diimbuhkan di dalam bahasa pemrograman lain.

* ### Wordpress
WordPress adalah platform penerbitan pribadi yang semantik, yang berfokus pada estetika, standar web, dan kegunaan. WordPress bersifat gratis, namun di sisi lain juga tak ternilai harganya. Pendek kata, WordPress ‘lah yang Anda perlukan ketika ingin membangun sebuah blog atau sebuah situs web yang cantik.

* ### Pluggin
Plugin adalah Aplikasi berukuran kecil yang ditanam ke dalam aplikasi lain yang lebih besar, yang bertujuan untuk meningkatkan fungsionalitas aplikasi induknya.

* ### SQLmap
sqlmap adalah tools opensource yang mendeteksi dan melakukan exploit pada bug SQL injection secara otomatis. dengan melakukan serangan SQL injection seorang attacker dapat mengambil alih serta memanipulasi sebuah database di dalam sebuah server.

* ### WPscan
WPScan adalah tools vulnerability scanner untuk CMS Wordpress yang ditulis dengan menggunakan bahasa pemrograman ruby, WPScan mampu mendeteksi kerentanan umum serta daftar semua plugin dan themes yang digunakan oleh sebuah website yang menggunakan CMS Wordpress.
___

## IMPLEMENTASI
* ### Instalasi Ubuntu Server
1.	Download Ubuntu Server pada https://www.ubuntu.com/download/server/thank-you?country=ID&version=16.04.3&architecture=amd64
 2. Buka VirtualBox
 3.	Klik New kemudian isikan nama, type, versi
 4.	Atur Ram . Sesuaikan pengaturan ram dengan spesifikasi hardware yang kita pakai, semakin besar ram yang kita alokasikan untuk virtual ubuntu server ini maka akan semakin cepat pula proses instalasi dan kinerjanya. Namun yang harus diingat adalah tidak boleh menghabiskan resource ram yang kita miliki. Semisal ram pada pc kita 6 gb kita bisa mengalokasikan 2 gb untuk virtual ubuntu server ini
 5.	Selanjutnya mensetting DISK DRIVE sebagai penyimpanan file system virtualisasi Ubuntu server. Pilih create a virtual hard disk now untuk membuat virtual penyimpanan
 6.	di bagian Storage on physical hard disk pilh Dynamically Allocated. Karena dengan begitu kita dapat lebih fleksibel dalam menggunakan virtual ruang penyimpanan
 7.	Mengatur tempat penyimpanan virtual ubuntu server dan kapasitas penyimpanan
 8.	Jalankan konfigurasi VirtualBox yang sebelumnya sudah di buat , kemudian masukan image iso ubuntu server 
 9.	Setelah image iso sudah di masukan kemudian klik start untuk memulai proses instalasi
 10.	Memilih bahasa
 11.	Klik install ubuntu server
 12.	Memilih bahasa yang gunakan saat proses intallasi
 13.	memilih lokasi, ini bertujuan untuk menentukan waktu pada ubuntu server
 14.	pilih benua atau wilayah asia karna Indonesia berada di asia tenggara
 15.	Pilih negara indonesia
 16.	Pilih United states
 17.	Deteksi keyboard yang kita gunakan, pilih no karna nantinya kita akan memasukan type keyboard secara manual
 18.	Pilih English (US). ini adalah keyboard yang umum digunakan oleh semua orang.
 19.	Pilih kembali English (us)
 20.	Masukan Hostname untuk system, masukan hostname tanpa spasi kemudian klik Continue
 21.	Masukan nama untuk user baru
 22.	Masukan username untuk user baru
 23.	Masukan password untuk user baru
 24.	Masukan ulang password untuk akun baru
 25.	Enkripsi directory home | system akan mengekripsi home jika kondisi anda belum masuk ke dalam system dan akan membuka enkripsi jika kita sudah masuk ke dalam system. Pilih no
 26.	Konfigurasi waktu | jika terdapat informasi pada layar yang menampilkan bahwa zona waktu anda adalah asia/Jakarta maka sudah benar. Kemudian pilih yes
 27.	Melakukan pertisi hardisk
 28.	Memilih disk yang akan di partisi
 29.	Klik yes
 30.	Masukan ukuran disk yang akan di gunakan untuk menginstall ubuntu server
 31.	Jika sudah selesai mengatur partisi disk, selanjutnya akan terdapat informasi pertisi yang sudah kita buat dan kemudian jika sudah yakin dengan partisi tersebut dan disk akan di format maka klik yes
 32.	Mengatur pembaruan pada system ubuntu server pilih no automatic update
 33.	Memilih software yang akan di pasang pada ubuntu server
 34.	Install GRUB boot | Klik yes
 35.	Jika instalasi telah selesai klik continue dan Virtualbox akan terestar kemudian coba login ke dalam sistem
 36.	Masukan username dan password yang sebelumnya telah di buat saat proses instalasi

* ### Instalasi Ubuntu Dekstop
1.	Download pada https://www.ubuntu.com/download
 2.	Membuat Virtual mesin dengan OS Ubuntu Dekstop 16.04. Mengisi nama virtual machine, type dan versi OS yang akan diinstall.
 3.	Mengatur ukuran memory RAM
 4.	Membuat virtual hard disk
 5.	Memilih tipe file hard disk. Ada banyak tipe Harddisk virtual, disini kita menggunakan VDI yaitu tipe standard yang digunakan VirtualBox,
 6.	Dynamically Allocated, hanya menggunakan alokasi harddisk yang terpakai. Sedangkan Fixed size akan mengalokasikan harddisk sesuai yang anda buat. Misalkan anda membuat harddisk dengan kapasitas 50GB, sedangkan yang terpakai hanya 20GB. Pada dynamic, harddisk real anda akan berkurang kapasitasnya 50GB, sedangkan pada Fixed, akan berkurang 20GB.
 7.	Tentukan nama harddisk virtual anda beserta ukurannya. Untuk Ubuntu saja, 8GB sudah cukup
 8.	Virtual Machine telah dibuat. Tinggal menambahkan file ISO Ubuntu untuk booting pertama kali. Klik Setting dan ikuti langkah selanjutnya.
 9.	Klik Storage.
 10.	Klik tombol CD disebelah Controller IDE.
 11.	Klik Choose disk untuk memilih file ISO Ubuntu.
 12.	Pilih file .iso Ubuntu, lalu klik open.
 13.	Klik OK.
 14.	Klik tombol start untuk booting menggunakan Ubuntu pada Virtual Machine yang telah kita buat.
 15.	Pilih bahasa yang akan digunakan pada Ubuntu.
 16.	Jika anda terhubung ke internet, dan ingin meng-install driver seperti graphic, Wifi, MP3 dan lainnya silakan centang pada pilihan kedua, jida tidak langsung klik “Continue”.
 17.	Memilih “Something else” untuk menentukan partisi dan alokasi sendiri.
 18.	Disini anda dapat melihat daftar harddisk. “/dev/sda” berarti harddisk pertama. Jika menghubungkan PC dengan 2 harddisk, maka akan tampil “dev/sdb”.
 19.	Klik harddisk yang akan di-install Ubuntu, lalu klik “newPartition Table” untuk membuat Partisi. Klik continue ketika muncul pesan konfirmasi untuk membuat partisi baru
 20.	Pada tampilan terlihat alokasi hardisk yang tersedia, yaitu 8.5GB. klik pada baris tersebut lalu klik tombol “+” untuk membuat partisi baru.
 21.	Berikut kita membuat partisi untuk swap, dengan alokasi 1GB. Klik “OK” untuk melanjutkan.
 22.	Partisi swap berhasil dibuat, klik “free space” lagi dan klik tombol “+” untuk membuat partisi baru lagi.
 23.	Selanjutnya kita membuat partisi dengan format Ext4 yang akan digunakan sebagai root folder “/” sebesar 7.5GB. Root folder “/” akan berisikan filesystem dan direktori home. Klik “OK” untuk lanjut.
 24.	Hasil akhir partisi akan sebagai berikut.
 25.	Anda juga dapat memisahkan direktori home anda dengan partisi lain dari root folder.
 26.	Ketika akan menyimpan perubahan partisi. klik “Continue” untuk lanjut.
 27.	Pilih zona waktu yang anda inginkan dengan klik pada peta, lalu klik “Continue”.
 28.	Pilih layout keyboard yang sesuai dengan keyboard anda, lalu klik “Continue”.
 29.	Isikan detail user yang akan digunakan pertama kali, lalu klik “Continue”.
 30.	Silakan tunggu sampai proses instalasi selesai.
 
* ### Instalasi Kali Linux
1.	Download Kali Linux pada https://www.kali.org/downloads
 2.	Buat Virtual Machine yang baru, Isikan Nama virtual machine, type : Linux, Version : Debian 64/32-bit, isikan jumlah alokasi memory pada contoh ini sebesar 1 GB / 1024 MB
 3.	Membuat virtual hard disk
 4.	Memilih tipe file hard disk. Ada banyak tipe Harddisk virtual, disini kita menggunakan VDI yaitu tipe standard yang digunakan VirtualBox,
 5.	Tentukan kapasitas harddisk minimum untuk kali Linux 20GB
 6.	Dynamically Allocated, hanya menggunakan alokasi harddisk yang terpakai. Sedangkan Fixed size akan mengalokasikan harddisk sesuai yang anda buat. Misalkan anda membuat harddisk dengan kapasitas 50GB, sedangkan yang terpakai hanya 20GB. Pada dynamic, harddisk real anda akan berkurang kapasitasnya 50GB, sedangkan pada Fixed, akan berkurang 20GB.
 7.	Pilih create dan Virtual Machine list anda bertambah
 8.	Jalankan VM dan untuk proses pertama anda diminta memasukan file .iso yang sudah didownload
 9.	Tunggu hingga muncul pilihan instalasi
10.	Pilih Graphical Instal
11.	Pilih Bahasa
12.	Pilih Lokasi
13.	Pilih Kombinasi Lokasi dan Bahasa
14.	Pilih Type Keyboard
15.	Buat nama server (kosongi jika tidak ada)
16.	Buat nama hostname
17.	Buat nama domain
18.	Buat password untuk 'root' system
19.	Pilih pembagian waktu, lalu continue
20.	Pilih Guided-use entire disk and set up LVM
21.	Pilih disk yang akan dipartisi
22. Pilih All files in one partition (recommended), lalu continue
23. Pilih Yes lalu continue
24. Pilih finish lalu continue
25. Pilih Yes lalu continue, tunggu hingga proses selesai. Setelah selesai pilih mirror network, lalu jika tidak menggunakan proxy, kosongkan kolom proxy, tekan continue
26. Jika mirror network gagal, tidak perlu menggunakan mirror network, pilih yes, lalu continue
27. Tunggu hingga proses selesai, dan muncul dialog instalasi GRUB, pilih yes lalu continue
28. Pilih device, lalu continue, tunggu hingga proses selesai
29. Pilih continue, instalasi telah selesai

* ### Instalasi Wordpress
1. Sebelum menginstall wordpress, anda harus menginstall MySQL server dan apache terlebih dahulu
2. Apabila sudah, install wordpress dengan mengetikkan perintah: sudo apt-get install wordpress
3. Kemudian masuklah kedalam mysql dengan mengetikkan perintah: mysql -u root -p, kemudian masukkan passwordnya
4. Jika sudah masuk ke mysql, buatlah database baru dengan perintah: CREATE DATABASE "NAMA_DATABASE";
5. Kalau database telah dibuat, ganti konfigurasi apache agar bisa mengakses wordpress. Buatlah file konfigurasi baru di /etc/apache2/sites-available dengan nama wordpress.conf
6. Lalu isi file wordpress.conf sesuai dengan gambar berikut. kalau sudah, simpan file konfigurasi tersebut.
7. Ketikkan perintah: sudo a2ensite wordpress untuk mengaktifkan konfigurasi. kemudian restart apache dengan mengetikkan systemctl restart apache2.service
8. Setelah membuat konfigurasi apache, sekarang kita membuat konfigurasi untuk database wordpressnya. masuklah pada folder wordpress, kemudian buatlah file konfigurasi dengan format penamaannya: [ip_virtual_box]-config.php
9. Isi file konfigurasi sebagai berikut. kalau sudah, simpan file konfigurasi lalu restart apache kembali.
10. Untuk mengecek konfigurasi, bukalah browser pada laptop anda, kemudian masukkan alamat sebagai berikut: ip/blog/wp-content
11. Apabila konfigurasi tadi benar, maka anda akan masuk kedalam halaman utama konfigurasi wordpress. apabila anda sudah masuk, isi konfigurasi sesuai keinginan anda.
12. Jika anda telah men-setting konfigurasi wordpress, lakukan login dengan username dan password sesuai konfigurasi yang anda lakukan barusan.
13. Jika login anda benar, maka anda akan masuk kedalam halaman utama wordpress sebagai admin.
* ### Instalasi Plugin
1. Sebelum menginstall plugin pada wordpress, ubah hak milik folder wp-content pada wordpress dengan mengetikkan: sudo chown -R :www-data wp-content
2. kemudian ubahlah ukuran upload maks pada php.ini agar bisa menginstall plugin yang berukuran lebih dari 2MB.
3. jika sudah, pada halaman utama wordpress sebelah kiri, pilih plugin->new plugin
4. kemudian cari plugin league manager dan spider web player. jika sudah unduh kedua plugin tersebut.
5. setelah terunduh, upload kedua plugin tersebut untuk diinstall.

* ### Instalasi SQLmap
 Pada kali linux, sqlmap merupakan aplikasi bawaan. Sedangkan pada ubuntu harus dilakukan proses instalasi sebagai berikut:
 1. Ketikkan perintah pada terminal sudo apt-get update
 2. Masukkan password
 3. Ketikkan perintah pada terminal sudo apt-get install sqlmap
 
* ### Instalasi WPscan

 Pada kali linux, WPScan merupakan aplikasi bawaan. Sedangkan pada ubuntu harus dilakukan proses instalasi sebagai berikut:
 1. Ketikkan perintah pada terminal apt-get install git
 2. Ketikkan perintah pada terminal sudo apt-get install libcurl4-openssl-dev libxml2 libxml2-dev libxslt1-dev ruby-dev build-essential libgmp-dev zlib1g-dev
 3. Ketikkan perintah pada terminal git clone https://github.com/wpscanteam/wpscan.git
 4. Ketikkan perintah pada terminal cd wpscan
 5. Ketikkan perintah pada terminal sudo gem install bundler && bundle install --without test development
 6. Ketikkan perintah pada terminal ruby wpscan.rb
___

## HASIL UJI COBA
* ### PENGUJIAN DENGAN SQLmap 
 1. Untuk mengetahui parameter yang vunerable dengan perintah, sqlmap --url="http://192.168.56.102/?match=1" --level 5 --risk 3 --dbms mysql 
  ![alt text](https://github.com/KharismaMonika/TUGAS2_PKSJ/blob/master/SCREENSHOOT/vulnrable%20param.JPG "Vunerable Parameter")
 
 
* ### PENGUJIAN DENGAN WPScan
 1. Menemukan user dengan mengetikkan perintah wpscan -u 192.168.56.102 -e -u
 ![alt text](https://github.com/KharismaMonika/TUGAS2_PKSJ/blob/master/SCREENSHOOT/wpscan1.JPG "User")
 

___

## PENUTUP
