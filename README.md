# Laporan Resmi Praktikum Jarkom Modul 3 2024

---
## Anggota Kelompok
- Rafika Az Zahra Kusumastuti  (5027231050)
- Johanes Edward Nathanael     (5027231067)

## Daftar Isi
- [Topologi](#topologi)
- [Nomor-0](#nomor-0)
- [Nomor-1](#nomor-1)
- [Nomor-2](#nomor-2)
- [Nomor-3](#nomor-3)
- [Nomor-4](#nomor-4)
- [Nomor-5](#nomor-5)
- [Nomor-6](#nomor-6)
- [Nomor-7](#nomor-7)
- [Nomor-8](#nomor-8)
- [Nomor-9](#nomor-9)
- [Nomor-10](#nomor-10)
- [Nomor-11](#nomor-11)
- [Nomor-12](#nomor-12)
- [Nomor-13](#nomor-13)

## Topologi
![Screenshot 2024-10-22 224446](https://github.com/user-attachments/assets/e0b9a50f-7d60-4963-94a9-832f7b257f6b)

### Network Configuration
Paradis (DHCP Relay)
```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 192.236.1.1
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 192.236.2.1
	netmask 255.255.255.0

auto eth3
iface eth3 inet static
	address 192.236.3.1
	netmask 255.255.255.0

auto eth4
iface eth4 inet static
	address 192.236.4.1
	netmask 255.255.255.0
```

Annie (Laravel Worker)
```
auto eth0
iface eth0 inet static
	address 192.236.1.2
	netmask 255.255.255.0
	gateway 192.236.1.1
```

Bertholdt (Laravel Worker)
```
auto eth0
iface eth0 inet static
	address 192.236.1.3
	netmask 255.255.255.0
	gateway 192.236.1.1
```

Reiner (Laravel Worker)
```
auto eth0
iface eth0 inet static
	address 192.236.1.4
	netmask 255.255.255.0
	gateway 192.236.1.1
```

Zeke (Client)
```
auto eth0
iface eth0 inet dhcp
```

Armin (PHP Worker)
```
auto eth0
iface eth0 inet static
	address 192.236.2.2
	netmask 255.255.255.0
	gateway 192.236.2.1
```

Eren (PHP Worker)
```
auto eth0
iface eth0 inet static
	address 192.236.2.3
	netmask 255.255.255.0
	gateway 192.236.2.1
```

Mikasa (PHP Worker)
```
auto eth0
iface eth0 inet static
	address 192.236.2.4
	netmask 255.255.255.0
	gateway 192.236.2.1
```

Erwin (Client) 
```
auto eth0
iface eth0 inet dhcp
```

Beast (Load Balancer Laravel)
```
auto eth0
iface eth0 inet static
	address 192.236.3.2
	netmask 255.255.255.0
	gateway 192.236.3.1
```

Colossal (Load Balancer PHP)
```
auto eth0
iface eth0 inet static
	address 192.236.3.3
	netmask 255.255.255.0
	gateway 192.236.3.1
```

Warhammer (Database Server)
```
auto eth0
iface eth0 inet static
	address 192.236.3.4
	netmask 255.255.255.0
	gateway 192.236.3.1
```

Fritz (DNS Server)
```
auto eth0
iface eth0 inet static
	address 192.236.4.2
	netmask 255.255.255.0
	gateway 192.236.4.1
```

Tybur (DHCP Server)
```
auto eth0
iface eth0 inet static
	address 192.236.4.3
	netmask 255.255.255.0
	gateway 192.236.4.1
```

### Install Dependencies
Paradis (DHCP Relay)
```
apt-get update
apt-get install isc-dhcp-relay -y
```

Tybur (DHCP Server)
```
apt-get update
apt-get install isc-dhcp-server -y
```

Fritz (DNS Server)
```
apt-get update
apt-get install bind9 -y
```

Beast dan Colossal (Load Balancer)
```
apt-get update
apt-get install apache2-utils -y
apt-get install nginx -y
apt-get install lynx -y
```

Warhammer (Database Server)
```
apt-get update
apt-get install mariadb-server -y
```

Annie, Bertholdt, dan Reiner (Laravel Worker)
```
apt-get update
apt-get install mariadb-server -y
```

Zeke dan Erwin (CLient)
```
apt-get update
apt-get install lynx -y
apt-get install htop -y
apt-get install apache2-utils -y
apt-get install jq -y
```


## Nomor 0
Pulau Paradis telah menjadi tempat yang damai selama 1000 tahun, namun kedamaian tersebut tidak bertahan selamanya. Perang antara kaum Marley dan Eldia telah mencapai puncak. Kaum Marley yang dipimpin oleh Zeke, me-register domain name marley.yyy.com untuk worker Laravel mengarah pada Annie. Namun ternyata tidak hanya kaum Marley saja yang berinisiasi, kaum Eldia ternyata sudah mendaftarkan domain name eldia.yyy.com untuk worker PHP (0) mengarah pada Armin.

## Nomor 1
Semua Client harus menggunakan konfigurasi ip address dari keluarga Tybur (dhcp).

## Nomor 2
Client yang melalui bangsa marley mendapatkan range IP dari [prefix IP].1.05 - [prefix IP].1.25 dan [prefix IP].1.50 - [prefix IP].1.100 (2)

## Nomor 3
Client yang melalui bangsa eldia mendapatkan range IP dari [prefix IP].2.09 - [prefix IP].2.27 dan [prefix IP].2 .81 - [prefix IP].2.243 (3)

## Nomor 4
Client mendapatkan DNS dari keluarga Fritz dan dapat terhubung dengan internet melalui DNS tersebut (4)

## Nomor 5
Dikarenakan keluarga Tybur tidak menyukai kaum eldia, maka mereka hanya meminjamkan ip address ke kaum eldia selama 6 menit. Namun untuk kaum marley, keluarga Tybur meminjamkan ip address selama 30 menit. Waktu maksimal dialokasikan untuk peminjaman alamat IP selama 87 menit. (5)

## Nomor 6
Armin berinisiasi untuk memerintahkan setiap worker PHP untuk melakukan konfigurasi virtual host untuk website berikut https://intip.in/BangsaEldia dengan menggunakan php 7.3 (6)

## Nomor 7
Dikarenakan Armin sudah mendapatkan kekuatan titan colossal, maka bantulah kaum eldia menggunakan colossal agar dapat bekerja sama dengan baik. Kemudian lakukan testing dengan 6000 request dan 200 request/second. (7)

## Nomor 8
Karena Erwin meminta “laporan kerja Armin”, maka dari itu buatlah analisis hasil testing dengan 1000 request dan 75 request/second untuk masing-masing algoritma Load Balancer dengan ketentuan sebagai berikut:
a. Nama Algoritma Load Balancer
b. Report hasil testing pada Apache Benchmark
c. Grafik request per second untuk masing masing algoritma. 
d. Analisis (8)

## Nomor 9
Dengan menggunakan algoritma Least-Connection, lakukan testing dengan menggunakan 3 worker, 2 worker, dan 1 worker sebanyak 1000 request dengan 10 request/second, kemudian tambahkan grafiknya pada “laporan kerja Armin”. (9)

## Nomor 10
Selanjutnya coba tambahkan keamanan dengan konfigurasi autentikasi di Colossal dengan dengan kombinasi username: “arminannie” dan password: “jrkmyyy”, dengan yyy merupakan kode kelompok. Terakhir simpan file “htpasswd” nya di /etc/nginx/supersecret/ (10)

## Nomor 11
Lalu buat untuk setiap request yang mengandung /titan akan di proxy passing menuju halaman https://attackontitan.fandom.com/wiki/Attack_on_Titan_Wiki (11) 
hint: (proxy_pass)

## Nomor 12
Selanjutnya Colossal ini hanya boleh diakses oleh client dengan IP [Prefix IP].1.77, [Prefix IP].1.88, [Prefix IP].2.144, dan [Prefix IP].2.156. (12) 
hint: (fixed in dulu clientnya)

## Nomor 13
Karena mengetahui bahwa ada keturunan marley yang mewarisi kekuatan titan, Zeke pun berinisiatif untuk menyimpan data data penting di Warhammer, dan semua data tersebut harus dapat diakses oleh anak buah kesayangannya, Annie, Reiner, dan Berthold.  (13)
