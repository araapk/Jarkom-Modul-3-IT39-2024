# Laporan Resmi Praktikum Jarkom Modul 3 2024

---
|Nama  | NRP |
|--|--|
| Johanes Edward Nathanael | 5027231057 |
| Rafika Az Zahra Kusumastuti | 5027231050 |

## Daftar Isi
- [Laporan Resmi Praktikum Jarkom Modul 3 2024](#laporan-resmi-praktikum-jarkom-modul-3-2024)
	- [Daftar Isi](#daftar-isi)
	- [Topologi](#topologi)
	- [Konfigurasi](#konfigurasi)
	- [Set .bashrc](#set-bashrc)
	- [Nomor 0](#nomor-0)
	- [Nomor 1](#nomor-1)
	- [Nomor 2](#nomor-2)
	- [Nomor 3](#nomor-3)
	- [Nomor 4](#nomor-4)
	- [Nomor 5](#nomor-5)
	- [Gabungan Nomor 1-5](#gabungan-nomor-1-5)
	- [Nomor 6](#nomor-6)
	- [Nomor 7](#nomor-7)
	- [Nomor 8](#nomor-8)
	- [Nomor 9](#nomor-9)
	- [Nomor 10](#nomor-10)
	- [Nomor 11](#nomor-11)
	- [Nomor 12](#nomor-12)
	- [Nomor 13](#nomor-13)

## Topologi
![Screenshot 2024-10-22 224446](https://github.com/user-attachments/assets/e0b9a50f-7d60-4963-94a9-832f7b257f6b)


## Konfigurasi

| **Name**      | **Interface** | **Address**   | **Netmask**        | **Gateway**   | **Configuration Type** |
|---------------|---------------|---------------|--------------------|--------------|------------------------|
| **Paradis**   | eth0          | -             | -                  | -            | DHCP                   |
|               | eth1          | 192.236.1.1     | 255.255.255.0      | -            | Static                 |
|               | eth2          | 192.236.2.1     | 255.255.255.0      | -            | Static                 |
|               | eth3          | 192.236.3.1     | 255.255.255.0      | -            | Static                 |
|               | eth4          | 192.236.4.1     | 255.255.255.0      | -            | Static                 |
| **Annie**     | eth0          | 192.236.1.2     | 255.255.255.0      | 192.236.1.1    | Static                 |
| **Berthold**  | eth0          | 192.236.1.3     | 255.255.255.0      | 192.236.1.1    | Static                 |
| **Reiner**    | eth0          | 192.236.1.4     | 255.255.255.0      | 192.236.1.1    | Static                 |
| **Armin**     | eth0          | 192.236.2.2     | 255.255.255.0      | 192.236.2.1    | Static                 |
| **Eren**      | eth0          | 192.236.2.3     | 255.255.255.0      | 192.236.2.1    | Static                 |
| **Mikasa**    | eth0          | 192.236.2.4     | 255.255.255.0      | 192.236.2.1    | Static                 |
| **Beast**     | eth0          | 192.236.3.2     | 255.255.255.0      | 192.236.3.1    | Static                 |
| **Colossal**  | eth0          | 192.236.3.3     | 255.255.255.0      | 192.236.3.1    | Static                 |
| **Warhammer** | eth0          | 192.236.3.4     | 255.255.255.0      | 192.236.3.1    | Static                 |
| **Fritz**     | eth0          | 192.236.4.2     | 255.255.255.0      | 192.236.4.1    | Static                 |
| **Tybur**     | eth0          | 192.236.4.3     | 255.255.255.0      | 192.236.4.1    | Static                 |
| **Zeke & Erwin** | eth0       | -             | -                  | -            | DHCP                   |


**Paradis (Router & DHCP Relay)**
```
# DHCP config for eth0
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

**Annie (Laravel Worker)**
```
auto eth0
iface eth0 inet static
	address 192.236.1.2
	netmask 255.255.255.0
	gateway 192.236.1.1
```

**Berthold (Laravel Worker)**
```
auto eth0
iface eth0 inet static
	address 192.236.1.3
	netmask 255.255.255.0
	gateway 192.236.1.1
```

**Reiner (Laravel Worker)**
```
auto eth0
iface eth0 inet static
	address 192.236.1.4
	netmask 255.255.255.0
	gateway 192.236.1.1
```

**Armin (PHP Worker)**
```
auto eth0
iface eth0 inet static
	address 192.236.2.2
	netmask 255.255.255.0
	gateway 192.236.2.1
```

**Eren (PHP Worker)**
```
auto eth0
iface eth0 inet static
	address 192.236.2.3
	netmask 255.255.255.0
	gateway 192.236.2.1
```

**Mikasa (PHP Worker)**
```
auto eth0
iface eth0 inet static
	address 192.236.2.4
	netmask 255.255.255.0
	gateway 192.236.2.1
```

**Beast (Laravel LB)**
```
auto eth0
iface eth0 inet static
	address 192.236.3.2
	netmask 255.255.255.0
	gateway 192.236.3.1
```

**Colossal (PHP LB)**
```
auto eth0
iface eth0 inet static
	address 192.236.3.3
	netmask 255.255.255.0
	gateway 192.236.3.1
```

**Warhammer (Database)**
```
auto eth0
iface eth0 inet static
	address 192.236.3.4
	netmask 255.255.255.0
	gateway 192.236.3.1
```

**Fritz (DNS Server)**

```
auto eth0
iface eth0 inet static
	address 192.236.4.2
	netmask 255.255.255.0
	gateway 192.236.4.1
```

**Tybur (DHCP Server)**

```
auto eth0
iface eth0 inet static
	address 192.236.4.3
	netmask 255.255.255.0
	gateway 192.236.4.1
```

**Zeke & Erwin (Client)**
```
auto eth0
iface eth0 inet dhcp
```

## Set .bashrc

**Paradis (DHCP Relay)**
```
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 192.236.0.0/16
apt-get update
apt-get install isc-dhcp-relay -y
service isc-dhcp-relay start
```

**Tybur (DHCP Server)**
```
echo 'nameserver 192.236.4.2' > /etc/resolv.conf
apt-get update
apt-get install isc-dhcp-server -y
service isc-dhcp-server restart
service isc-dhcp-server status
```

**Fritz (DNS Server)**
```
echo 'nameserver 192.168.122.1' > /etc/resolv.conf
apt-get update
apt-get install bind9 -y
```

**Warhammer (Database Server)**
```
echo 'nameserver 192.236.4.2' > /etc/resolv.conf
apt-get update
apt-get install mariadb-server -y
```

**Beast & Colossal (Load Balancer)**
```
echo 'nameserver 192.236.4.2' > /etc/resolv.conf
apt-get update
apt-get install bind9 apache2-utils nginx -y

service nginx start
```

**Annie, Bertholdt, Reiner (Laravel Worker)**
``` 
echo 'nameserver 10.74.4.2' > /etc/resolv.conf
apt-get update
apt-get install mariadb-client -y
```

**Armin, Eren, Mikasa (PHP Worker)**
```
echo 'nameserver 192.236.4.2' > /etc/resolv.conf
apt-get update
apt-get install lynx curl unzip nginx software-properties-common php7.3 php7.3-fpm -y
```

**Zeke & Erwin (Client)**
```
apt-get update
apt-get install lynx htop apache2-utils jq -y
```


## Nomor 0
Pulau Paradis telah menjadi tempat yang damai selama 1000 tahun, namun kedamaian tersebut tidak bertahan selamanya. Perang antara kaum Marley dan Eldia telah mencapai puncak. Kaum Marley yang dipimpin oleh Zeke, me-register domain name marley.yyy.com untuk worker Laravel mengarah pada Annie. Namun ternyata tidak hanya kaum Marley saja yang berinisiasi, kaum Eldia ternyata sudah mendaftarkan domain name eldia.yyy.com untuk worker PHP (0) mengarah pada Armin.

Buat script pada DNS Server atau Fritz
```
apt-get update
apt-get install bind9 -y

forward="options {
directory \"/var/cache/bind\";
forwarders {
  	   192.168.122.1;
};

allow-query{any;};
listen-on-v6 { any; };
};
"
echo "$forward" > /etc/bind/named.conf.options

echo "zone \"marley.it39.com\" {
	type master;
	file \"/etc/bind/jarkom/marley.it39.com\";
};

zone \"eldia.it39.com\" {
	type master;
	file \"/etc/bind/jarkom/eldia.it39.com\";
};
" > /etc/bind/named.conf.local

mkdir /etc/bind/jarkom

riegel="
;
;BIND data file for local loopback interface
;
\$TTL    604800
@    IN    SOA    marley.it39.com. root.marley.it39.com. (
        2        ; Serial
                604800        ; Refresh
                86400        ; Retry
                2419200        ; Expire
                604800 )    ; Negative Cache TTL
;                   
@    IN    NS    marley.it39.com.
@       IN    A    192.236.1.2
"
echo "$riegel" > /etc/bind/jarkom/marley.it39.com

granz="
;
;BIND data file for local loopback interface
;
\$TTL    604800
@    IN    SOA    eldia.it39.com. root.eldia.it39.com. (
        2        ; Serial
                604800        ; Refresh
                86400        ; Retry
                2419200        ; Expire
                604800 )    ; Negative Cache TTL
;                   
@    IN    NS    eldia.it39.com.
@       IN    A    192.236.2.2
"
echo "$granz" > /etc/bind/jarkom/eldia.it39.com

service bind9 restart
```



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

## Gabungan Nomor 1-5
Buat script di Router (DHCP Relay)) atau Paradis
```
apt-get update
apt install isc-dhcp-relay -y

service isc-dhcp-relay start 

echo '# Defaults for isc-dhcp-relay initscript

# sourced by /etc/init.d/isc-dhcp-relay
# installed at /etc/default/isc-dhcp-relay by the maintainer scripts

#
# This is a POSIX shell fragment
#

# What servers should the DHCP relay forward requests to?
SERVERS="192.236.4.3" 

# On what interfaces should the DHCP relay (dhrelay) serve DHCP requests?
INTERFACES="eth1 eth2 eth3 eth4"

# Additional options that are passed to the DHCP relay daemon?
OPTIONS=""' > /etc/default/isc-dhcp-relay


echo net.ipv4.ip_forward=1 > /etc/sysctl.conf

service isc-dhcp-relay restart
```

Kemudian buat script di DHCP Server atau Tybur
```
apt-get update
apt-get install isc-dhcp-server -y

echo 'INTERFACESv4="eth0"
INTERFACESv6=""
' > /etc/default/isc-dhcp-server

subnet="option domain-name \"example.org\";
option domain-name-servers ns1.example.org, ns2.example.org;

default-lease-time 600;
max-lease-time 7200;

ddns-update-style-none;

subnet 192.236.1.0 netmask 255.255.255.0 {
    range 192.236.1.5 192.236.1.25;
    range 192.236.1.50 192.236.1.100;
    option routers 192.236.1.1;
    option broadcast-address 192.236.1.255;
    option domain-name-servers 192.236.4.2;
    default-lease-time 360;
    max-lease-time 5220;
}

subnet 192.236.2.0 netmask 255.255.255.0 {
    range 192.236.2.9 192.236.2.27;
    range 192.236.2.81 192.236.2.243;
    option routers 192.236.2.1;
    option broadcast-address 192.236.2.255;
    option domain-name-servers 192.236.4.2;
    default-lease-time 1800;
    max-lease-time 5220;
}

subnet 192.236.3.0 netmask 255.255.255.0 {
}

subnet 192.236.4.0 netmask 255.255.255.0 {
}

"
echo "$subnet" > /etc/dhcp/dhcpd.conf

service isc-dhcp-server restart
```
![Screenshot 2024-10-27 222621](https://github.com/user-attachments/assets/e1038658-c351-4278-98cc-9dce3950cfe2)
![Screenshot 2024-10-27 222635](https://github.com/user-attachments/assets/2e314295-031c-443d-b44a-0ba880922cf7)



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
