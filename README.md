# Project Nmap : Network Discovery & Port Scanning

## 📌 Deskripsi
Di project ini saya belajar memakai Nmap untuk mencari perangkat yang aktif dan layanan apa yang berjalan di dalamnya.Hasilnya saya dokumentasikan berdasarkan temuan dan rekomendasi mitigasinya.

## 🖥️ Environment
|  Mesin        | Sistem Operasi | IP Address   | Peran                    |
|---------------|----------------|--------------|--------------------------|
|Laptop (host)  | Windows 11     |10.10.10.1    |Menjalankan Nmap (Scanner)|
|VirtualBox     | Kali Linux     |10.10.10.16   |Target                    |

- Jaringan VirtualBox : Host-Only
- Tool : Nmap versi 7.991

## ⚙️ Persiapan
- Windows 11 
  
      1. Install Nmap dari website resminya https://nmap.org/
      2. Buka Command Promt atau PowerShell dengan klik kanan lalu pilih Run as administrator
      3. Cek instalasi dan IP laptop :
         nmap --version
         ipconfig
    
     
- Kali Linux (VM)
