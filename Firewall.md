# 🔥 Tutorial Firewall Mikrotik dengan Berbagai Cara & Protokol

Firewall di Mikrotik bisa digunakan untuk **filtering, NAT, mangle, hingga raw**.  
Dokumentasi ini berisi contoh konfigurasi **dasar hingga menengah** untuk berbagai kebutuhan.

---

## 🛠️ 1. Blokir IP Tertentu
Blokir akses dari host tertentu (contoh: `192.168.1.100`).
```bash
/ip firewall filter add chain=forward src-address=192.168.1.100 action=drop
````

---

## 🌐 2. Blokir Akses Port (TCP/UDP)

Blokir **FTP (TCP/21)** dari semua client.

```bash
/ip firewall filter add chain=forward protocol=tcp dst-port=21 action=drop
```

Blokir **DNS (UDP/53)** untuk user tertentu.

```bash
/ip firewall filter add chain=forward src-address=192.168.1.50 protocol=udp dst-port=53 action=drop
```

---

## 📶 3. Blokir Ping (ICMP)

Blokir ping ke router dari interface WAN.

```bash
/ip firewall filter add chain=input protocol=icmp in-interface=ether1 action=drop
```

Blokir semua ping keluar-masuk.

```bash
/ip firewall filter add chain=forward protocol=icmp action=drop
```

---

## 🔄 4. Filtering Berdasarkan Interface

Izinkan hanya trafik dari LAN masuk ke router.

```bash
/ip firewall filter add chain=input in-interface=ether2 action=accept
/ip firewall filter add chain=input in-interface=ether1 action=drop
```

---

## 🌐 5. Filtering Berdasarkan Layer7 Protocol

Blokir akses ke **YouTube** menggunakan regex.

```bash
/ip firewall layer7-protocol add name=youtube regexp="^.+(youtube.com|ytimg.com).*\$"
/ip firewall filter add chain=forward layer7-protocol=youtube action=drop
```

---

## ⚡ 6. NAT Masquerade (Berbagi Internet)

Izinkan client LAN mengakses internet via router.

```bash
/ip firewall nat add chain=srcnat out-interface=ether1 action=masquerade
```

---

## 🔀 7. Redirect Port (Port Forwarding)

Arahkan trafik HTTP dari luar ke server web lokal (`192.168.1.10`).

```bash
/ip firewall nat add chain=dstnat protocol=tcp dst-port=80 in-interface=ether1 action=dst-nat to-addresses=192.168.1.10
```

---

## 📋 8. Drop Berdasarkan Address List

Tambahkan IP ke blacklist lalu drop.

```bash
/ip firewall address-list add list=blacklist address=192.168.1.50
/ip firewall filter add chain=forward src-address-list=blacklist action=drop
```

---

## 📉 9. Rate Limit (Mencegah Flood/DDOS)

Batasi ping ke router max 10 paket per detik.

```bash
/ip firewall filter add chain=input protocol=icmp limit=10,5 action=accept
/ip firewall filter add chain=input protocol=icmp action=drop
```

---

## 🚫 10. Block Port Range

Blokir **port 135–139 (NetBIOS)** untuk keamanan.

```bash
/ip firewall filter add chain=forward protocol=tcp dst-port=135-139 action=drop
```

---
