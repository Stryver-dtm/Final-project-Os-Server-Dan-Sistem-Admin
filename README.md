# Final-project-Os-Server-Dan-Sistem-Admin

## Final Project

Membuat Layanan Web Server di **Ubuntu Desktop 22.04.3** dengan spesifikasi berikut:
- **RAM**: 4 GB  
- **Processor**: 3 CPU  
- **Disk**: 32 GB

## Layanan Yang Digunakan
1. [Apache2 (Web Server)](#1-nginx-web-server)
2. [MySQL (Database Server)](#2-mysql-dabase-server)
3. [PHP (Backend Server)](#3-php-backend-server)
4. [Redis (Cache Server)](#4-redis-cache-server)
5. [Let's Encrypt (SSL/TLS)](#5-lets-encrypt)

## Daftar Isi
1. [Apache2 (Web Server)](#1-nginx-web-server)
2. [MySQL (Database Server)](#2-mysql-dabase-server)
3. [PHP (Backend Server)](#3-php-backend-server)
4. [Redis (Cache Server)](#4-redis-cache-server)
5. [Let's Encrypt (SSL/TLS)](#5-lets-encrypt)
6. [Konfigurasi Apache2](#6-Konfigurasi-apache2)
7. [Konfigurasi Mysql dan php](#7-Konfigurasi-Mysql-dan-php)
8. [Menghubungkan Redis dengan Apache2](#8-Menghubungkan-Redis-dengan-Apache2)

## Installation
## 1. Apache2 (Web Server)
Penjelasan tentang instalasi dan konfigurasi Nginx (Web Server).
Langkah 1: Install Apache2
```
sudo apt install apache2
```
Langkah 2: jalankan Apache2
```
sudo systemctl start apache2
```
Langkah 3: aktifkan Apache2
```
sudo systemctl enable apache2
```
Langkah 4: Buka browser dan akses
```
https://ip-address
```
![img](https://github.com/Stryver-dtm/Final-project-Os-Server-Dan-Sistem-Admin/blob/main/apache.png?raw=true)
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

## 6.Konfigurasi Apache2
1. Buat Folder Proyek
Buat folder proyek di dalam direktori root Apache. Folder ini akan berisi home, produk, dan kontak.

Perintah untuk Membuat Folder:
```
sudo mkdir /var/www/html/proyek-saya
sudo mkdir /var/www/html/proyek-saya/home
sudo mkdir /var/www/html/proyek-saya/produk
sudo mkdir /var/www/html/proyek-saya/kontak
```
2. Ubah Hak Akses (Opsional)
Agar folder dapat diakses oleh pengguna biasa:
```
sudo chown -R $USER:$USER /var/www/html/proyek-saya
sudo chmod -R 755 /var/www/html/proyek-saya
```
3. Tambahkan File HTML
Buat file HTML di setiap folder (home, produk, dan kontak).
Tambahkan file html pada folder home
```
nano /var/www/html/proyek-saya/home/index.html
```
4. Tambahkan file html pada folder produk
```
nano /var/www/html/proyek-saya/produk/index.html
```
5. Tambahkan file html pada folder kontak
```
nano /var/www/html/proyek-saya/kontak/index.html
```
6. Restart Apache
Setelah semua file dan folder selesai dibuat, restart Apache untuk memastikan perubahan diterapkan:
```
sudo systemctl restart apache2
```
7. Akses File HTML di Browser
Gunakan browser untuk mengakses halaman-halaman tersebut:
```
http://localhost/proyek-saya/home
```
8. Untuk membuat ketiga halaman HTML (home, produk, dan kontak) dapat diakses dari satu halaman utama, Anda perlu membuat 
sebuah halaman utama yang memiliki navigasi ke ketiga halaman tersebut.
Rubah pada bagian ini agar semua halaman bisa terkoneksi

```
 <a href="/proyek-saya/home">Halaman Home</a>
        <a href="/proyek-saya/produk">Halaman Produk</a>
        <a href="/proyek-saya/kontak">Halaman Kontak</a>
```
9. Akses Halaman Utama
Setelah menyimpan file, restart Apache:
```
sudo systemctl restart apache2
```
10. Buka browser dan buka browser:
```
http://localhost/proyek-saya/home
```
dan kalian sudah menghubungkan semua halaman 

11.Berikut hasil dari konfigurasi diatas:
![img](https://github.com/Stryver-dtm/Final-project-Os-Server-Dan-Sistem-Admin/blob/main/1.png?raw=true)
![img](https://github.com/Stryver-dtm/Final-project-Os-Server-Dan-Sistem-Admin/blob/main/2.png?raw=true)
![img](https://github.com/Stryver-dtm/Final-project-Os-Server-Dan-Sistem-Admin/blob/main/3.png?raw=true)

## 7.Konfigurasi Mysql dan php
1 .Amankan instalasi MySQL:
```
sudo mysql_secure_installation
```
Ikuti langkah-langkah untuk mengatur kata sandi root dan mengamankan instalasi.

2 .Masuk ke MySQL untuk menguji koneksi:
```
sudo mysql -u root -p
```

3 .Setelah masuk, Anda dapat membuat database dan user:
```
CREATE DATABASE nama_database;
CREATE USER 'user_baru'@'localhost' IDENTIFIED BY 'password_baru';
GRANT ALL PRIVILEGES ON nama_database.* TO 'user_baru'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```
4 .Periksa apakah modul PHP sudah aktif di Apache:
```
sudo a2enmod php
```
5. Kemudian restart apache:
```
sudo systemctl restart apache2
```

## 8.Menghubungkan Redis dengan Apache2:
Redis biasanya digunakan sebagai cache untuk meningkatkan kinerja aplikasi web. Anda dapat mengintegrasikannya dengan Apache2 menggunakan modul atau alat seperti PHP (jika aplikasi Anda berbasis PHP).

Langkah-langkah:

1. Konfigurasi Redis:

Edit file konfigurasi Redis (/etc/redis/redis.conf) untuk memastikan Redis berjalan dengan aman.
Pastikan Redis berjalan sebagai daemon:
```
supervised systemd
```
2. Instal Redis Extension untuk PHP (opsional): Jika Anda menggunakan PHP, instal ekstensi Redis:
```
sudo apt install php-redis
```
3. Restart Apache2: Setelah Redis diatur dan ekstensi diinstal, restart Apache2:
```
sudo systemctl restart apache2
```

## 9.Menggunakan Let's Encrypt untuk HTTPS di Apache2:

Langkah-langkah:

1. Instal Certbot: Certbot adalah alat untuk mengelola sertifikat SSL dari Let's Encrypt.
```
sudo apt update
sudo apt install certbot python3-certbot-apache
```
2. Memasang Sertifikat SSL: Jalankan perintah berikut untuk mengonfigurasi HTTPS otomatis:
```
sudo certbot --apache
```
Anda akan diminta untuk memilih domain dan mengonfirmasi pengalihan otomatis dari HTTP ke HTTPS.

3. Otomatisasi Pembaruan Sertifikat: Let's Encrypt sertifikat berlaku selama 90 hari. Anda dapat mengotomatiskan pembaruannya dengan cron job:
```
sudo crontab -e
```
Tambahkan baris berikut untuk pembaruan otomatis:
```
0 3 * * * certbot renew --quiet
```
4.Verifikasi Konfigurasi SSL: Pastikan situs Anda berjalan dengan HTTPS menggunakan:
```
sudo systemctl restart apache2
```
Redis digunakan untuk caching dan dapat diintegrasikan dengan aplikasi menggunakan modul atau ekstensi PHP.
Let's Encrypt menyediakan SSL gratis untuk mengamankan situs web Anda, dan Certbot membantu mengintegrasikan sertifikat tersebut dengan Apache2.
