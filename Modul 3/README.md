# Mengolah Nilai dengan Python

## Konsep
### Pengertian Python
<br><br><img src= "https://www.python.org/static/community_logos/python-logo-master-v3-TM-flattened.png" style="height:90px;width:auto"><br><br>
Python, salah satu bahasa pemrograman paling populer di dunia, telah menciptakan segalanya mulai dari algoritma rekomendasi Netflix hingga software yang mampu mengontrol mobil yang bisa mengemudi sendiri. Python adalah bahasa pemrograman yang dirancang untuk digunakan dalam berbagai aplikasi, termasuk ilmu data, pengembangan software dan website, otomatisasi, serta umumnya mampu menyelesaikan pekerjaan lainnya.

## Koneksi VPN
Dikarenakan Raspberry yang berada di lab KCKS yang menggunakan jaringan dari ITS, maka untuk melakukan koneksi SSH diperlukan VPN dan juga one-time-password yang bisa didapatkan dari website my.its.ac.id

1. Masuk dan Login ke my.its.ac.id
2. Masuk ke bagian One-time-password
3. Pilih Tambah Akses VPN
4. Download Konfigurasi OpenVPN (my.its.ac.id)
5. Download OpenVPN
6. Import konfigurasi OpenVPN 
7. Selesai

## Installasi VnC
Apabila melakukan koneksi melalui SSH hanya diberikan tampilan terminal, apabila menggunakan VnC bisa mendapatkan tampilan GUI. yang perlu dilakukan adalah

1. Download VnC Viewer
2. Lakukan Installasi
3. Login menggunakan klasterdti@gmail.com
4. Password menggunakan klasterdti1959
5. Lakukan koneksi ke salah satu Node


## Install MariaDB
Karena mau menggunakan SQL maka harus install SQL service, disini menggunakan MariaDB

1. sudo apt update
2. sudo apt-get install mariadb-server
3. sudo mysql_secure_installation
4. sudo mariadb --version
5. Jalankan commands
```
cd /var/lib/mysql
ls
rm -r *
mysql_install_db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
systemctl restart mysqld
systemctl restart mysql.service
systemctl restart mariadb
mysql -uroot
```

Apabila sudah menunjukan versi dari mariadb, maka sudah berhasil

Referensi : 
https://pimylifeup.com/raspberry-pi-mysql/

## Install Python
Untuk menjalankan program script yang diberikan oleh Bapak Dwi, diperlukan python maka dilakukan installasi python

1. sudo apt-get update
2. sudo apt-get install python3.8 python3-pip
3. sudo python --version 
4. sudo pip --version

Pastikan python dan pip sudah terinstall


Referensi : https://realpython.com/installing-python/


## Install Library tambahan

Adapula beberapa library yang diperlukan untuk run program python yang diberikan, beberapanya adalah BoundedProcessor, pandas dll.

1. pip install pandas
2. pip install bounded-pool-executor
3. pip install mysql


## Download Database
Untuk mendapatkan DB yang telah disiapkan maka perlu dilakukan download dari google drive dengan command 

1. 
```
wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=1oIB6H7KsGQcz2OEVlVWD6oKttmCNsWk-' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=1oIB6H7KsGQcz2OEVlVWD6oKttmCNsWk-" -O cbtjatimsm.tar.gz && rm -rf /tmp/cookies.txt
```
2. tar -xvf cbtjatimsm.tar.gz 
3. Pindah ke root (sudo -i), 
4. mv hasil export ke root
5. Jalankan command 
6. Lalu melakukan import database yang telah didownload kedalam MariaDB server, ikuti langkah yang ada di Readme (Didalam hasil export cbtjatimsm.tar.gz)

## Program Python

## Referensi
https://www.wartaekonomi.co.id/read366664/apa-itu-bahasa-pemrograman-python<br>
