### Backlog Minggu Kedua

- [Konfigurasi Router](#konfigurasi-router)
  - [Reset Router](#reset-router)
  - [Konfigurasi](#konfigurasi)
    - [IP Public](#ip-public)
    - [IP Local](#ip-local)
    - [Default Route](#default-route)
    - [DNS](#dns)
    - [Internet Client](#internet-client)
    - [Dan berikut konfigurasi lengkapnya](#dan-berikut-konfigurasi-lengkapnya)


# Konfigurasi Router

## Reset Router

Pertama adalah me-_reset_ router agar konfigurasi pada router dikembalikan ke konfigurasi pabrik. Untuk reset router, bisa menggunakan perintah dibawah pada **Terminal** winbox

```console
/system
reset-configuration no-defaults=yes skip-backup=yes
```

## Konfigurasi

### IP Public

Untuk menambah _config_ untuk IP public, kita bisa menggunakan perintah berikut untuk mengatur port `ether1` untuk _public_

[![Whats-App-Image-2023-03-10-at-15-37-28.jpg](https://i.postimg.cc/Kz6tKbN1/Whats-App-Image-2023-03-10-at-15-37-28.jpg)](https://postimg.cc/1nK8TLbS)

### IP Local

Untuk menambah _config_ untuk IP lokal, kita bisa menggunakan perintah berikut untuk mengatur port `ether2` untuk lokal

[![Whats-App-Image-2023-03-10-at-15-37-28.jpg](https://i.postimg.cc/Kz6tKbN1/Whats-App-Image-2023-03-10-at-15-37-28.jpg)](https://postimg.cc/1nK8TLbS)

### Default Route

Untuk default route, atur menggunakan 

[![Whats-App-Image-2023-03-10-at-15-40-31.jpg](https://i.postimg.cc/pd166923/Whats-App-Image-2023-03-10-at-15-40-31.jpg)](https://postimg.cc/GBGKBmTj)
[![Whats-App-Image-2023-03-10-at-15-40-55.jpg](https://i.postimg.cc/P5VytBBw/Whats-App-Image-2023-03-10-at-15-40-55.jpg)](https://postimg.cc/CRDk76Mh)
### DNS

untuk mengatur DNS pada router

[![Whats-App-Image-2023-03-10-at-15-43-00.jpg](https://i.postimg.cc/QCS5f7DT/Whats-App-Image-2023-03-10-at-15-43-00.jpg)](https://postimg.cc/p5hpTppW)


### Internet Client

Untuk _config client_, config yang diterapkan hanya DHCP server karena _client_ hanya tinggal IP nya saja menggunakan perintah

```console
/ip pool
add name=dhcp_pool0 ranges=192.168.3.2-192.168.3.254
/ip dhcp-server network
add address=192.168.3.0/24 gateway=192.168.3.1
/ip dhcp-server
add address-pool=dhcp_pool0 disabled=no interface=ether2 name=dhcp1
```
[![Whats-App-Image-2023-03-10-at-15-44-55.jpg](https://i.postimg.cc/Vk7wzkfW/Whats-App-Image-2023-03-10-at-15-44-55.jpg)](https://postimg.cc/WdJCnjJd)
[![Whats-App-Image-2023-03-10-at-15-45-08.jpg](https://i.postimg.cc/yd4bHMZT/Whats-App-Image-2023-03-10-at-15-45-08.jpg)](https://postimg.cc/FfpZbnGf)


### Dan berikut konfigurasi lengkapnya

```console
# mar/10/2023 07:46:55 by RouterOS 6.39.3
# software id = SSDE-WU5D
#
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip pool
add name=dhcp_pool0 ranges=192.168.3.2-192.168.3.254
/ip dhcp-server
add address-pool=dhcp_pool0 disabled=no interface=ether2 name=dhcp1
/ip address
add address=10.252.108.15/24 interface=ether1 network=10.252.108.0
add address=192.168.3.1/24 interface=ether2 network=192.168.3.0
/ip dhcp-server network
add address=192.168.3.0/24 gateway=192.168.3.1
/ip dns
set servers=202.9.85.3
/ip firewall nat
add action=masquerade chain=srcnat out-interface=ether1
/ip route
add distance=1 gateway=10.252.108.212
/system identity
set name=Kel-3
```
[![Whats-App-Image-2023-03-10-at-15-47-21.jpg](https://i.postimg.cc/pLQ9C8BX/Whats-App-Image-2023-03-10-at-15-47-21.jpg)](https://postimg.cc/NKMffKVW)

[def]: #backlog-minggu-kedua
