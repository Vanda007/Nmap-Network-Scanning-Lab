# 📍Project Nmap : Network Discovery & Port Scanning

## 📌 Deskripsi
Project ini berisi catatan latihan saya dalam menggunakan Nmap untuk melakukan network discovery dan port scanning. Di sini, saya mensimulasikan pengujian dari mesin host Windwows 11 dan target Kali Linux di virtualbox untuk mencari perangkat yang aktif, melihat port yang terbuka, serta mengetahui layanan apa saja yang berjalan di dalamanya.

---

## 🖥️ Environment
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
Tujuan : mencari tahu perangkat apa saja yang aktif di jaringan lab

Command :
```bash
nmap -sn 10.10.10.16/24
```

Hasil :
(gambar ss)

Penjelasan :
- -sn artinya untuk mengecek perangkat yang aktif, tanpa mengecek port
- 
