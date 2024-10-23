# Laporan Resmi Praktikum Jarkom Modul 3 2024

---
## Anggota Kelompok
- Rafika Az Zahra Kusumastuti  (5027231050)
- Johanes Edward Nathanael     (5027231067)

## Daftar Isi
- [Topologi](#topologi)
- [Nomor-0](#nomor-0)

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

