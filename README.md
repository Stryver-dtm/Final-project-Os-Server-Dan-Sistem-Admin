# Final-project-Os-Server-Dan-Sistem-Admin

## Final Project

Membuat Layanan Web Server di **Ubuntu Desktop 22.04.3** dengan spesifikasi berikut:
- **RAM**: 4 GB  
- **Processor**: 3 CPU  
- **Disk**: 32 GB

## Daftar Isi
1. [1. Nginx (Web Server)](#1-nginx-web-server)
2. [2. MySQL (Database Server)](#2-mysql-dabase-server)
3. [3. PHP (Backend Server)](#3-php-backend-server)
4. [4. Redis (Cache Server)](#4-redis-cache-server)
5. [5. Let's Encrypt (SSL/TLS)](#5-lets-encrypt)

## Installation
## 1. Nginx (Web Server)
Penjelasan tentang instalasi dan konfigurasi Nginx (Web Server).
Langkah 1: Install Nginx
```
sudo apt install nginx -y
```
Langkah 2: jalankan Nginx
```
sudo systemctl start nginx
```
Langkah 3: aktifkan nginx 
```
sudo systemctl enable nginx
```
Langkah 4: Buka browser dan akses 
```
https://ip-address
```
## 2.MySQL (Database Server)
Penjelasan tentang instalasi MySQL.
Langkah 1: Install MySQL
```
sudo apt install mysql-server -y
```
Langkah 2: Verifikasi instalasi: MySQL
```
mysql --version
```
Langkah 3:Aktifkan Layanan MySQL
```
ssudo systemctl start mysql
```
Langkah 4: Aktifkan agar berjalan otomatis saat booting:
```
sudo systemctl enable mysql 
```
Langkah 5: Uji Koneksi MySQL
1.Masuk Ke MySQL
```
sudo mysql -u root -p
```
2.Setelah masuk, Anda akan melihat prompt MySQL seperti ini:
```
mysql>
```
## 3.PHP (Backend Server)
enjelasan tentang instalasi
1.Tambahkan repositori tambahan
```
sudo apt install software-properties-common -y
sudo add-apt-repository ppa:ondrej/php -y
sudo apt update
```
2.Instal PHP dengan perintah:
```
sudo apt install php -y
```
3.Verifikasi instalasi:
```
php -v
```
## 4.Redis (Cache Server)
1.Instal Redis dengan perintah berikut:
```
sudo apt install redis-server -y
```
2.Verifikasi instalasi Redis:
```
redis-server --version
```
3.Mulai dan Aktifkan Redis
```
sudo systemctl start redis
```
4.Aktifkan layanan Redis agar berjalan otomatis saat booting:
```
sudo systemctl enable redis
```
5.Periksa status Redis:
```
sudo systemctl status redis
```
## 5.Let's Encrypt (SSL/TLS)
1. Instal Certbot dan Plugin Web Server
   Nginx
   ```
   sudo apt install certbot python3-certbot-nginx -y
   ```
2.Dapatkan Sertifikat SSL
```
sudo certbot --nginx
```
3.Uji Sertifikat SSL
```
https://yourdomain.com
```
4.Konfigurasi Firewall
```
sudo ufw allow
sudo ufw reload
```

