# 📍Project Nmap : Network Discovery & Port Scanning

## 📌 Deskripsi
Project ini berisi catatan latihan saya dalam menggunakan Nmap untuk melakukan network discovery dan port scanning. Di sini, saya mensimulasikan pengujian dari mesin host Windwows 11 dan target Kali Linux di virtualbox untuk mencari perangkat yang aktif, melihat port yang terbuka, serta mengetahui layanan apa saja yang berjalan di dalamanya.

---

## 🖥️ Lab Environment
|  Mesin        | Sistem Operasi | IP Address   | Peran                    |
|---------------|----------------|--------------|--------------------------|
|Laptop (host)  | Windows 11     |10.10.10.1    |Menjalankan Nmap (Scanner)|
|VirtualBox     | Kali Linux     |10.10.10.16   |Target                    |

- Jaringan VirtualBox : Host-Only
- Tool : Nmap versi 7.991

---

## 📝 Persiapan
- Windows 11 
  
      1. Install Nmap dari website resminya https://nmap.org/
      2. Buka Command Prompt atau PowerShell dengan klik kanan lalu pilih Run as administrator
      3. Cek instalasi dan IP laptop :
          nmap --version
          ipconfig
     
- Kali Linux (VM)

      1. Cek IP Kali :
         ip a
      2. Aktifkan beberapa layanan :
          sudo systemctll start ssh
          sudo systemctl start apache2

### Tes koneksi dari Windows :
Buka Command Prompt lalu ketik :
```bash
ping 10.10.10.16
```

---

## 🛠️ Praktek
### 1. Cari Perangkat Aktif
Tujuan : mendeteksi apakah perangkat target aktif dan dapat dijangkau di jaringan lokal menggunakan Nmap tanpa melakukan pemindaian port.

Command :
```bash
nmap -sn 10.10.10.16/24
```

Hasil :
(gambar ss)

Penjelasan :
- '-sn' artinya untuk mengecek perangkat yang aktif, tanpa mengecek port
- Ditemukan 3 perangkat aktif : 10.10.10.1 (Windows), 10.10.10.2 dan 10.10.10.16 (VM Virtualbox)

### 2. Cek Port Terbuka
Tujuan : melihat port mana saja yang terbuka di target

Command :
```bash
nmap 10.10.10.16
```

Hasil :
(gambar)

Penejelasan :
- Status open artinya ada layanan yang sedang aktif di port itu
- Port yang open : Port 22 untuk SSH dan Port 80 untuk http/web

### 3. Cek Layanan dan Versinya
Tujuan : mengidentifikasi jenis layanan dan versi software yang berjalan pada port terbuka.

Command :
```bash
nmap -sV 10.10.10.16
```

Hasil :
(gambar)

Penjelasan :
- 'sV' mecoba mendeteksi versi layanan yang berjalan pada port terbuka
- Port 22 : OpenSSH 10.4p1 Debian 5
- Port 80 : Apache httpd 2.4.68 Debian
- OS : Linux
  
### 4. Identifikasi Sistem Operasi
Tujuan : mendeteksi jenis dan versi sistem operasi yang dipakai target

Command :
```bash
nmap -O 10.10.10.16
```

Hasil :

Penjelasan :
- Perintah ini harus dijalankan lewat CMD/PowerShell as administrator
- 
