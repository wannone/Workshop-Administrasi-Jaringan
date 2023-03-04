# Identifikasi Kernel

Kernel Linux adalah inti dari sistem operasi Linux yang bertanggung jawab untuk mengontrol dan mengelola sumber daya komputer serta menjembatani komunikasi antara perangkat keras dan perangkat lunak aplikasi. Kernel Linux mengatur sistem file, jaringan, keamanan, dan berbagai hal lainnya yang berkaitan dengan pengoperasian sistem operasi Linux secara keseluruhan.

Untuk menampilkan kernel yang digunakan pada distro, kita bisa menggunakan perintah `uname -a` pada terminal.

[![image.png](https://i.postimg.cc/0QkYKL0y/image.png)](https://postimg.cc/SXP2w1PB)

**penjelasan kernel** :
Pada gambar diatas, kernel yang digunakan adalah versi 4.15.0-156-generic.
- 4 Adalah nomor utama Kernel
- 15 adalah nomor minor kernel
- 0 adalah nomor revisi kernel
- 156 adalah nomor pembangunan kernel

# Identifikasi Directory root pada linux
[![image.png](https://i.postimg.cc/d3vV0Y25/image.png)](https://postimg.cc/5Y7VPDkz)
Berikut adalah beberapa folder pada direktori / atau root pada sistem operasi Linux beserta fungsinya:
1. /bin: Folder ini berisi program yang diperlukan oleh sistem operasi Linux untuk menjalankan fungsi dasar, seperti shell dan command-line utilities.
2. /boot: Folder ini berisi file sistem boot, termasuk kernel Linux dan konfigurasinya.
3. /dev: Folder ini berisi file perangkat, termasuk perangkat keras dan virtual.
4. /etc: Folder ini berisi file konfigurasi sistem dan aplikasi.
5. /home: Folder ini berisi direktori pengguna di sistem Linux.
6. /lib: Folder ini berisi pustaka (library) yang diperlukan oleh program di sistem Linux.
7. /media: Folder ini berisi mount point untuk media yang terhubung ke sistem Linux, seperti CD-ROM dan USB drive.
8. /mnt: Folder ini berisi mount point untuk sistem file tambahan yang terhubung ke sistem Linux.
9. /opt: Folder ini berisi aplikasi tambahan yang tidak termasuk dalam instalasi sistem Linux standar.
10. /proc: Folder ini berisi informasi tentang proses yang sedang berjalan di sistem Linux.
11. /root: Folder ini adalah direktori rumah (home directory) untuk pengguna root di sistem Linux.
12. /run: Folder ini berisi file runtime, termasuk file socket dan PID.
13. /sbin: Folder ini berisi program yang diperlukan oleh sistem operasi Linux untuk menjalankan fungsi sistem yang lebih kompleks.
14. /srv: Folder ini berisi data service yang disediakan oleh sistem Linux.
15. /tmp: Folder ini berisi file sementara (temporary) yang dihasilkan oleh aplikasi atau sistem operasi Linux.
16. /usr: Folder ini berisi file sistem dan aplikasi yang digunakan oleh pengguna di sistem Linux.
17. /var: Folder ini berisi file variabel, termasuk log sistem dan cache aplikasi.

Setiap folder pada direktori / memiliki fungsi dan tujuan tertentu dalam menjalankan sistem operasi Linux dan mendukung aplikasi di dalamnya.

# Perbedaan sudo dan su

Kedua perintah sudo dan su digunakan pada sistem operasi Linux untuk memperoleh hak akses root atau superuser. Namun, ada beberapa perbedaan antara kedua perintah tersebut, yaitu:

1. sudo (superuser do) digunakan untuk menjalankan perintah dengan hak akses superuser sementara atau untuk mengizinkan pengguna untuk menjalankan perintah dengan hak akses superuser tanpa harus login sebagai root. Dalam hal ini, pengguna harus memasukkan kata sandi mereka terlebih dahulu untuk mendapatkan hak akses superuser sementara.
2. su (switch user) digunakan untuk login sebagai pengguna superuser atau root secara permanen. Dalam hal ini, pengguna harus memasukkan kata sandi superuser atau root untuk login sebagai pengguna superuser.
3. Perintah sudo memungkinkan pengguna untuk menjalankan perintah dengan hak akses superuser tanpa harus mengetahui kata sandi superuser atau root. Sedangkan, perintah su memerlukan pengguna untuk mengetahui kata sandi superuser atau root untuk login sebagai pengguna superuser.
4. sudo lebih aman dari segi keamanan karena pengguna hanya diberikan hak akses superuser sementara untuk menjalankan perintah tertentu, sedangkan su memberikan pengguna akses superuser secara permanen selama sesi login.

Dalam penggunaan sehari-hari, sudo sering digunakan oleh pengguna Linux untuk menjalankan perintah tertentu dengan hak akses superuser sementara, sedangkan su digunakan oleh administrator sistem untuk login sebagai pengguna superuser atau root untuk melakukan tugas-tugas administratif yang memerlukan hak akses superuser secara permanen.

```bash
# super user ke home user
sudo su

# ke root
sudo su -
```
[![image.png](https://i.postimg.cc/26pZ43RG/image.png)](https://postimg.cc/gwDjpz0L)

# Repository

Repositori Linux adalah tempat penyimpanan perangkat lunak untuk sistem operasi Linux, seperti aplikasi, pustaka, dan driver perangkat keras. Repositori ini dapat diakses melalui internet dan digunakan untuk menginstal dan memperbarui perangkat lunak pada sistem operasi Linux secara mudah dan aman.

Untuk melihat repository mana saja yang digunakan pada sistem, kita bisa menggunakan perintah `cat /etc/apt/source.list`.

Ada beberapa jenis repository pada linux:
1. `deb cdrom` adalah repository dari CD/DVD instalasi Ubuntu.
2. `deb http://id.archive.ubuntu.com/ubuntu/ kinetic main restricted` adalah repository utama (main) Ubuntu, yang berisi paket-paket utama untuk sistem operasi Ubuntu.
3. `deb http://id.archive.ubuntu.com/ubuntu/ kinetic-updates main restricted` adalah repository Ubuntu untuk pembaruan (updates) dari paket-paket di repository utama.
4. `deb http://id.archive.ubuntu.com/ubuntu/ kinetic universe` adalah repository Ubuntu untuk paket-paket yang tidak disupport secara resmi oleh Ubuntu, namun tetap terbuka untuk diakses oleh pengguna.
5. `deb http://security.ubuntu.com/ubuntu kinetic-security multiverse` adalah repository Ubuntu untuk pembaruan keamanan (security) dari paket-paket di repository multiverse.
6. `deb http://security.ubuntu.com/ubuntu kinetic-security universe` Ini adalah repository Ubuntu untuk pembaruan keamanan (security) dari paket-paket di repository universe.
7. `deb http://security.ubuntu.com/ubuntu kinetic-security main restricted` Ini adalah repository Ubuntu untuk pembaruan keamanan (security) dari paket-paket di repository utama.

# Package Manager
Package manager pada Linux adalah perangkat lunak yang digunakan untuk mengatur, menginstal, memperbarui, dan menghapus perangkat lunak pada sistem operasi Linux. Package manager pada Linux dapat memudahkan pengguna dalam mencari dan menginstal perangkat lunak yang dibutuhkan, serta memastikan bahwa perangkat lunak yang diinstal selalu terbaru dan aman.

Package manager pada Linux terdiri dari beberapa jenis, di antaranya adalah:
1. Advanced Packaging Tool (APT): Package manager yang biasa digunakan pada distribusi Linux berbasis Debian, seperti Ubuntu, Linux Mint, dan lain-lain.
2. Yellowdog Updater Modified (YUM): Package manager yang biasa digunakan pada distribusi Linux berbasis Red Hat, seperti Fedora, CentOS, dan lain-lain.
3. Pacman: Package manager yang biasa digunakan pada distribusi Linux Arch Linux.
4. Zypper: Package manager yang biasa digunakan pada distribusi Linux SUSE.
5. Portage: Package manager yang biasa digunakan pada distribusi Linux Gentoo.

Setiap package manager memiliki kelebihan dan kekurangan masing-masing, serta digunakan pada distribusi Linux tertentu. Namun, fungsi utama package manager pada Linux tetap sama, yaitu memudahkan pengguna dalam mengelola perangkat lunak pada sistem operasi Linux.
