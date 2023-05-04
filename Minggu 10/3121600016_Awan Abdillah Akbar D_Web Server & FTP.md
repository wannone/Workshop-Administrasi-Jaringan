LAPORAN RESMI

KONSEP JARINGAN


![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.001.png)



|<p></p><p>Dr. Ferry Astika Saputra ST, M.Sc.</p>|
| :- |




Nama	: Awan Abdillah Akbar D

Kelas	: D4 Teknik Informatika - A

NRP	: 3121600016

**Instal Web Serever dan FTP pada Ubuntu**

1. **Web Server**

Sebelum memulai, pastikan apache sudah terinstal terlebih dahulu. Untuk menginstal apache seperti gambar di bawah lalu tunggu hingga selesai.

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.002.png)

Jika sudah selesai, cek ip yang didapat dari virtual box dengan mengetik “ifconfig”. Terlihat pada ip yang didapat  adalah 192.168.1.11

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.003.png)

Jika sudah mendapatkan ip cek pada browser lalu ketik ip tersebut. Jika berhasil maka akan muncul tampilan web Apache2

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.004.png)

Lalu kembali pada terminal dan instal php, tunggu hingga proses selesai

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.005.png)

Jika sudah selesai, masuk ke folder html dengan mengetik “cd /var/www/html” lalu ketik nano phpinfo.php untuk membuat file phpinfo

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.006.png)

Setelah masuk ke file tersebut ketikan kode seperti gambar di bawah di dalam file tersebut

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.007.png)

Jika sudah selesai, restart apache dengan mengetik seperti di bawah

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.008.png)

Lalu cek apakah php sudah terpasang pada web service dengan membuka browser lalu ketik ip yang di dapat tadi lalu tambahkan “/phpinfo.php”

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.009.png)

Jika sudah berhasil, instal phpmyadmin dan tunggu hingga selesai

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.010.png)

Jika sudah selesai menginstal ketik command seperti berikut, jika berhasil maka mysql sudah terinstal pada ubuntu

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.011.png)

Lalu cek pada browser dengan mengetik ip lalu tambahkan “/phpmyadmin”

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.012.png)

Jika sudah berhasil, kembali ke terminal lalu buat folder yang berisi web yang akan ditampilkan dan buat file index.html

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.013.png)

Lalu buat website sederhana menggunakan html untuk ditampilkan di browser lokal

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.014.png)

Setelah selesai membuat, restart apache dan pergi ke browser untuk mengecek website yang sudah dibuat

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.015.png)

Pergi ke browser lalu tambahkan folder website yang dibuat sebelumnya

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.016.png)

Pada tampilan website yang saya buat menggunakan logika setelah 4 detik langsung diarahkan ke halaman landing page produk saya

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.017.png)



1. **FTP Server**

Sebelum memulai instal ftp terlebih dahulu dan tunggu hingga selesai

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.018.png)

Setelah berhasil instal, buat user baru untuk dipasang ftp

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.019.png)

Setelah berhasil membuat akun, buat folder data di dalam user yang dibuat sebelumnya. Lalu ikuti command seperti di bawah dan menambahkan password pada ftp tersebut dan mengubah akses baca dengan chmod. Setelah itu buka file proftpd.conf

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.020.png)

Setelah itu ubah server name yang diinginkan

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.021.png)

Lalu pergi ke bagian paling bawah dan tambahkan kode seperti berikut

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.022.png)

Setelah selesai konfigurasi ftp, restart ftp server dan lihat status tersebut, jika terdapat active running maka ftp server berhasil dijalankan.

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.023.png)

Setelah itu buka brwoser dan ketik server name yang di masukkan sebelumnya

![](Aspose.Words.be706e20-718e-42c2-8828-571406c10eca.024.png)









