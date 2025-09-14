# 📑 Mikrotik CLI Cheat Sheet (40 Perintah Dasar)

Berikut ringkasan 40 perintah dasar Mikrotik dalam bentuk tabel agar mudah digunakan saat praktik atau ujian.

---

| No | Perintah CLI | Fungsi |
|----|--------------|--------|
| 1  | `/system identity set name=Maul-Suka-Belajar` | Mengubah nama router |
| 2  | `/ip address add address=192.168.10.1/24 interface=ether1` | Menambahkan IP ke interface |
| 3  | `/user set 0 password=PasswordBaru123` | Mengganti password admin |
| 4  | `/ip address print` | Melihat daftar IP |
| 5  | `/system shutdown` | Mematikan router |
| 6  | `/system reboot` | Restart router |
| 7  | `/system reset-configuration` | Reset konfigurasi |
| 8  | `/interface set ether1 name=lubang1` | Mengganti nama interface |
| 9  | `/ping 192.168.10.1` | Ping ke IP |
| 10 | `/ip firewall nat add chain=srcnat action=accept` | NAT dengan srcnat |
| 11 | `/ip firewall nat add chain=srcnat action=masquerade out-interface=ether1` | NAT masquerade (berbagi internet) |
| 12 | `/interface print` | Melihat daftar interface |
| 13 | `/ip route add gateway=192.168.1.1` | Menambah gateway manual |
| 14 | `/ip dns set servers=8.8.8.8` | Menambah DNS manual |
| 15 | `/ip route print` | Melihat daftar gateway |
| 16 | `/ip dns print` | Melihat daftar DNS |
| 17 | `/ip dhcp-server setup` | Membuat DHCP server |
| 18 | `/ip dhcp-server remove 0` | Menghapus DHCP |
| 19 | `/ip address print` | Melihat daftar IP |
| 20 | `/ip route remove 0` | Menghapus gateway |
| 21 | `/ip dhcp-server print` | Melihat konfigurasi DHCP server |
| 22 | `/ip dhcp-client add interface=ether2 disabled=no` | Menjadi DHCP client |
| 23 | `/log print` | Melihat log |
| 24 | `/interface bridge add name=bridge1` | Membuat bridge |
| 25 | `/interface bridge port add bridge=bridge1 interface=ether2` | Menambah interface ke bridge |
| 26 | `/tool telnet 192.168.1.1` | Remote router via telnet |
| 27 | `/interface l2tp-server server set enabled=yes` | Menjalankan L2TP server |
| 28 | `/ip dhcp-client remove 0` | Menghapus DHCP client |
| 29 | `/ip address disable 0` | Menonaktifkan IP address |
| 30 | `/interface l2tp-client add connect-to=1.2.3.4 user=test password=123 disabled=no` | Registrasi ke L2TP server |
| 31 | `/system identity print` | Melihat nama router |
| 32 | `/file print` | Melihat daftar file |
| 33 | `/system resource print` | Melihat info router |
| 34 | `/system package print` | Melihat paket RouterOS |
| 35 | `/system clock print` | Melihat waktu |
| 36 | `/user add name=mahasiswa password=12345 group=full` | Menambah user |
| 37 | `/user print` | Melihat daftar user |
| 38 | `/system backup save name=backup-config` | Membackup konfigurasi |
| 39 | `/system backup load name=backup-config` | Restore konfigurasi |
| 40 | `/ip firewall filter print` | Melihat daftar firewall |
