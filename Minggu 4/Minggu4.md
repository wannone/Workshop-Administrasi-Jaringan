# KONFIGURASI DNS SERVER

Lakukan konfigurasi pada file-file berikut ini:
1. Membuat domain dari server linux dengan menggunakan TLD (Top Level Domain). TLD ini hanya berfungsi pada jaringan lokal saja. Langkahnya adalah dengan mengkonfigurasi file named.conf yang terdapat pada direktori /etc/bind. File ini berfungsi sebagai informasi zona dan direkori file forward dan reserve. Perintahnya adalah :

        dengan perintah: home/sis# nano /etc/bind/named.conf
        
    Jika sudah berada di editor silahkan tambahkan sesuai dengan tanda merah seperti di bawah ini, jangan lupa di simpan hasil menambahkan dengan perintah ctrl+o dan ctrl+x untuk keluar. 
    
    [![Whats-App-Image-2023-04-06-at-10-51-23.jpg](https://i.postimg.cc/C1v17cBY/Whats-App-Image-2023-04-06-at-10-51-23.jpg)](https://postimg.cc/XGC47ckD)
    File forward berfungsi untuk mengkonversi alamat domain ke alamat IP, sedangkan file reverse berlaku sebaliknya yaitu mengkonversi alamat IP server ke domain.
    
2. Buatlah file forward dengan cara mengcopy file db.local yang terletak pada direktori /etc/bind:

    [![Whats-App-Image-2023-04-06-at-10-51-21.jpg](https://i.postimg.cc/rscBdTFw/Whats-App-Image-2023-04-06-at-10-51-21.jpg)](https://postimg.cc/ft22F69G)
    Buka file forward:
    
        dengan perintah: nano /etc/bin/forward
    
    Ganti localhost dengan hostname “smkn1pacitan.net” seperti yang sudah di buat sebelumnya, sehingga menjadi seperti berikut:
    
    [![Whats-App-Image-2023-04-06-at-10-51-25.jpg](https://i.postimg.cc/sXZSNBSv/Whats-App-Image-2023-04-06-at-10-51-25.jpg)](https://postimg.cc/vgbc1Z0s)
    ganti juga IP dengan IP Address Server kita.

3. Selanjutnya membuat file reserve dengan cara mengcopy file db.127 pada direktori yang sama dengan forward:

    [![Whats-App-Image-2023-04-06-at-10-51-24.jpg](https://i.postimg.cc/VkC85mjX/Whats-App-Image-2023-04-06-at-10-51-24.jpg)](https://postimg.cc/yDs5bqpN)
    
    Konfigurasi file reverse dengan mengetikkan perintah berikut:
    
        dengan perintah: home/sis# nano /etc/bind/reverse
    
    Ganti localhost dengan alamat hostname seperti file forward di atas:

    [![Whats-App-Image-2023-04-06-at-10-51-26.jpg](https://i.postimg.cc/kgKgzxhr/Whats-App-Image-2023-04-06-at-10-51-26.jpg)](https://postimg.cc/qNBrCCTQ)
    
    Ganti juga alamat IP 1.0.0 dengan IP Oktet terakhir IP Debian kita.
    
    [![Whats-App-Image-2023-04-06-at-10-51-28.jpg](https://i.postimg.cc/PJ1d9H2W/Whats-App-Image-2023-04-06-at-10-51-28.jpg)](https://postimg.cc/H8sG8qGn)
    
4. Tambahkan DNS nameserver dari server linux pada file resolv.conf dengan perintah berikut:

        dengan perintah: /home/sis# nano /etc/resolv.conf
    
    Pastikan nameserver (IP Address Server Debian )berada pada baris pertama.
    
    [![Whats-App-Image-2023-04-06-at-10-51-27.jpg](https://i.postimg.cc/GmmxLmGm/Whats-App-Image-2023-04-06-at-10-51-27.jpg)](https://postimg.cc/RN2HG9gk)
    
5. Restart layanan DNS server seperti perintah sebelumnya:

    [![Whats-App-Image-2023-04-06-at-10-51-29.jpg](https://i.postimg.cc/66RXc97q/Whats-App-Image-2023-04-06-at-10-51-29.jpg)](https://postimg.cc/s1VqDC4C)
    
    PENGUJIAN DNS SERVER
    
    Test apakah DNS Server tersebut berhasil atau tidak, dengan perintah ping maupun nslookup dari computer server.

    Install terlebih dahulu layanan dnsutils dengan perintah:
    
    [![Whats-App-Image-2023-04-06-at-10-51-31.jpg](https://i.postimg.cc/HLLM08nq/Whats-App-Image-2023-04-06-at-10-51-31.jpg)](https://postimg.cc/pmgyRTDC)
    
    Lakukan pengujian dengan melakukan perintah berikut:
    
        dengan perintah: /home/sis# nslookup takehome.net
    
    Lakukan juga pengujian dengna cara mengetikkan perintah berikut:
    
        /home/sis# nslookup 192.168.1.1
    
    Pengujian pada komputer client dapat dilakukan dengan cara memasukkan alamat domain pada url bar browser atau dengan menggunakan utilitas ping.

    Demikian pembahasan singkat terkait dengan konfigurasi DNS server pada distro Linux Debian 
