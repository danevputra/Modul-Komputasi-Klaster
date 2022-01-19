# Mengolah Data dengan Python

## Konsep
### Pengertian Python
<br><br><img src= "https://www.python.org/static/community_logos/python-logo-master-v3-TM-flattened.png" style="height:90px;width:auto"><br><br>
Python, salah satu bahasa pemrograman paling populer di dunia, telah menciptakan segalanya mulai dari algoritma rekomendasi Netflix hingga software yang mampu mengontrol mobil yang bisa mengemudi sendiri. Python adalah bahasa pemrograman yang dirancang untuk digunakan dalam berbagai aplikasi, termasuk ilmu data, pengembangan software dan website, otomatisasi, serta umumnya mampu menyelesaikan pekerjaan lainnya.

## Instalasi VnC
Apabila melakukan koneksi melalui SSH hanya diberikan tampilan terminal, apabila menggunakan VnC bisa mendapatkan tampilan GUI. yang perlu dilakukan adalah

1. Download VnC Viewer
2. Lakukan Installasi
3. Login menggunakan klasterdti@gmail.com
4. Password menggunakan klasterdti1959
5. Lakukan koneksi ke salah satu Node

## Koneksi VPN
Dikarenakan Raspberry yang berada di lab KCKS yang menggunakan jaringan dari ITS, maka untuk melakukan koneksi SSH diperlukan VPN dan juga one-time-password yang bisa didapatkan dari website my.its.ac.id

1. Masuk dan Login ke my.its.ac.id
2. Masuk ke bagian One-time-password
3. Pilih Tambah Akses VPN
4. Download Konfigurasi OpenVPN (my.its.ac.id)
5. Download OpenVPN
6. Import konfigurasi OpenVPN 
7. Selesai

## Install MariaDB
Karena mau menggunakan SQL maka harus install SQL service, disini menggunakan MariaDB

1. sudo apt update
2. sudo apt-get install mariadb-server
3. sudo mysql_secure_installation
4. sudo mariadb --version (jika berjalan maka mariadb sudah terinstall)
5. Jalankan commands
```bash
cd /var/lib/mysql
ls
rm -r *
mysql_install_db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
systemctl restart mysqld
systemctl restart mysql.service
systemctl restart mariadb
mysql -uroot
CREATE USER 'klaster'@'%' IDENTIFIED BY 'Klaster123';
GRANT ALL ON *.* TO 'cluster'@'%';
FLUSH PRIVILEGES;
quit;
```

## Install Python
Untuk menjalankan program script yang diberikan oleh Bapak Dwi, diperlukan python maka dilakukan installasi python

1. sudo apt-get update
2. sudo apt-get install python3.9 python3-pip
3. sudo python --version (jika berjalan maka python berhasil diinstall)
4. sudo pip --version (jika berjalan maka pip berhasil diinstall)

## Install Library tambahan

Adapula beberapa library yang diperlukan untuk run program python yang diberikan, beberapanya adalah BoundedProcessor, pandas dll.

1. pip install pandas
2. pip install bounded-pool-executor
3. pip install mysql


## Download Database
Untuk mendapatkan DB yang telah disiapkan maka perlu dilakukan download dari google drive dengan command 

1. 
```bash
wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=1oIB6H7KsGQcz2OEVlVWD6oKttmCNsWk-' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=1oIB6H7KsGQcz2OEVlVWD6oKttmCNsWk-" -O cbtjatimsm.tar.gz && rm -rf /tmp/cookies.txt
```
2. tar -xvf cbtjatimsm.tar.gz 
3. Pindah ke root (sudo -i), 
4. mv hasil export ke root
5. Lalu melakukan import database yang telah didownload kedalam MariaDB server, ikuti langkah yang ada di Readme (Didalam hasil export cbtjatimsm.tar.gz)

## Program Python
Jika sudah berhasil melakukan semua langkah, terakhir jalankan program berikut
```python
import mysql.connector as connection
import time
import pandas as pd
import psutil
from bounded_pool_executor import BoundedProcessPoolExecutor
import warnings

warnings.filterwarnings("ignore")


def loadDB(id_kota):
    t = time.time()
    try:
        mydb = connection.connect(host="Localhost",
                                  database='CBT_JATIM',
                                  user="klaster",
                                  password="Klaster123", use_pure=True)

        query = 'select id_siswa, nama, nrp, value, jawaban_benar, id_mapel from soal_jawaban where id_kota=%d;' % id_kota
        ujian_siswa = pd.read_sql(query, mydb)

        mydb.close()  # close the connection
    except Exception as e:
        mydb.close()
        print(str(e))

    elapsed = time.time() - t
    print("Time Load DB  = {:.3f}".format(elapsed))
    ujian_siswa.loc[ujian_siswa['value'] ==
                    ujian_siswa['jawaban_benar'], ['score']] = 1
    ujian_siswa = ujian_siswa.fillna(0)
    result = ujian_siswa.groupby(['id_siswa', 'nama', 'nrp', 'id_mapel'])[
        'score'].agg('sum')
    # result = ujian_siswa.groupby(['id_siswa'])['score'].sum()
    result.to_csv("id_kota_%d.csv" % id_kota)


if __name__ == '__main__':

    tAll = time.time()
    n_jobs = psutil.cpu_count()
    print("Ready to worker")
    cnt = 0
    with BoundedProcessPoolExecutor(max_workers=n_jobs) as worker:
        for id_kota in range(1,2):
            print('#%d Worker initialization %s' % (cnt, id_kota))
            cnt += 1
            print("Load DB %d, please wait ..." % id_kota)
            worker.submit(loadDB, id_kota)
    elapsed = time.time() - tAll
    print("Time selesai  = {:.3f}".format(elapsed))
```

## Install Python pada Windows
1. Download software python disini ([Download](https://www.python.org/downloads/))  sesuaikan dengan versi windows yang anda gunakan.
2. Double click pada software python yang telah didownload.<br><br><img src= "https://www.itnotbad.com/wp-content/uploads/2020/12/cara-install-python-39-img2.png" style="height:200px;width:auto"><br><br>
3. Centang Install launcher for all user (recommended) dan Add Python 3.9 to PATH untuk penambahan path command Python, Lalu Jalankan proses Klik Install Now dan klik Yes bila ada notifikasi<br><br><img src= "https://www.itnotbad.com/wp-content/uploads/2021/01/cara-install-python-39-img3.png" style="height:200px;width:auto"><br><br>
4. Proses Setup sedang berjalan, harap tunggu dan jangan sampai tekan close<br><br><img src= "https://www.itnotbad.com/wp-content/uploads/2020/12/cara-install-python-39-img4.png" style="height:300px;width:auto"><br><br>
5. Proses Setup telah selesai, Click Close, Kita lanjut untuk test aplikasi dan test coding.<br><br><img src= "https://www.itnotbad.com/wp-content/uploads/2020/12/cara-install-python-39-img5.png" style="height:200px;width:auto"><br><br>
6. Buka aplikasi python, Klik Windows => Semua aplikasi => Python 3.9 => Python 3.9 (64-bit).<br><br><img src= "https://www.itnotbad.com/wp-content/uploads/2021/01/cara-install-python-39-img6.png" style="height:200px;width:auto"><br><br>
7. Kita akan menguji dengan perintah print (“Hello world”).<br><br><img src= "https://www.itnotbad.com/wp-content/uploads/2021/01/cara-install-python-39-img7.png" style="height:200px;width:auto"><br><br>
8. Cara lain untuk menjalankan program python di windows adalah dengan mengetikkan command ```py namafile.py``` di command prompt, namun sebelum itu kita harus menyiapkan sebuah file, buatlah file hello.py sebagai berikut.
9. Kemudian buka command prompt dan jalankan perintah ```py hello.py```
10. Sebenarnya command ```py namafile.py``` mirip jika kita akan menjalankan program python pada linux, hanya saja di linux kita gunakan command ```python3 namafile.py```

## Referensi
https://www.wartaekonomi.co.id/read366664/apa-itu-bahasa-pemrograman-python<br>
https://pimylifeup.com/raspberry-pi-mysql/<br>
https://realpython.com/installing-python/<br>
https://www.itnotbad.com/cara-install-python-3-9-di-windows-10-untuk-belajar-programing/<br>
