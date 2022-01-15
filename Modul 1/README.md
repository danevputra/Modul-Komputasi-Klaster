# Database & Query
## 1. Konsep
### A. Pengertian Database
Database atau basis data adalah kumpulan data yang dikelola sedemikian rupa berdasarkan ketentuan tertentu yang saling berhubungan sehingga mudah dalam pengelolaannya. Melalui pengelolaan tersebut pengguna dapat memperoleh kemudahan dalam mencari informasi, menyimpan informasi dan membuang informasi.
### B. Pengertian Query
Pengertian Query adalah kemampuan untuk menampilkan data dari database untuk diolah lebih lanjut yang biasanya diambil dari tabel tabel dalam database. Pengertian query yang lain adalah pertanyaan (question) atau permintaan (order) informasi tertentu daru sebuah database yang tertulis dalam format tertentu.
### C. Contoh Produk Database
1. Oracle RDBMS<br><br><img src= "https://www.fujitsu.com/lu/Images/oracle-db580x224_tcm67-40873.jpg" style="height:90px;width:auto"><br><br>
    Oracle adalah relational database management system (RDBMS) untuk mengelola informasi secara terbuka, komprehensif dan terintegrasi. Biasa digunakan untuk pengaksesan data yang dilakukan secara online. Dirancang khusus untuk organisasi berukuran besar, bukan untuk ukuran kecil dan menengah.<br><br>
   Kelebihan dari Oracle
   - Banyak fitur yang dapat memenuhi tuntutan fleksibilitas dari organisasi besar.
   - Dapat mendayagunakan lebih dari satu server serta data storage dengan mudah dan transparan.
   
   Kekurangan dari Oracle
   - DBMS yang paling rumit dan paling mahal di dunia. Penggunaannya memakan banyak biaya, mulai dari device sampai diperlukannya DBA yang handal.
2. MySQL<br><br><img src= "https://cdns.klimg.com/merdeka.com/i/w/news/2021/03/03/1280790/540x270/mysql-adalah-sistem-manajemen-berbasis-data-ketahui-cara-kerjanya.png" style="height:90px;width:auto"><br><br>
     MYSQL adalah singkatan “My Structured Query Language”. Program ini berjalan sebagai server menyediakan multi-user mengakses ke sejumlah database. multithread, multi-user, dengan sekitar 6 juta instalasi di seluruh dunia. MySQL AB gratis, dibawah lisensi GNU General Public License (GPL), tetapi ada juga MySQL yang berbayar.<br><br>
    Kelebihan MySQL
    - Free Stabil dan tangguh
    - Fleksibel dengan berbagai pemrograman
    - Security yang baik
    - Dukungan dari banyak komunitas
    - Kemudahan management database
    - Mendukung transaksi
    - Perkembangan software cukup cepat
    
    Kekurangan MySQL
    - Kurang mendukung koneksi ke bahasa pemrograman visual seperti VB, Delphi, dan Foxpro dikarenakan koneksi ini menyebabkan field yang dibaca harus sesuai dengan koneksi dari program visual tersebut.
    - Data yang ditangani belum begitu besar.
    - Lambat untuk query yang kompleks seperti LEFT JOIN yang banyak, dan penggunaan SubQuery.
    - Belum mendukung Windowing Function

3. MongoDB<br><br><img src= "https://www.nurulfikri.com/wp-content/uploads/2020/02/MongoDB-mdb.png" style="height:90px;width:auto"><br><br>
    MongoDB (dari "humongous") adalah sistem basis data berorentasi dokumen lintas platform. Diklasifikasikan sebagai basis data "NoSQL", MongoDB menghindari struktur basis data relasional tabel berbasis tradisional yang mendukung JSON seperti dokumen dengan skema dinamis (MongoDB menyebutnya sebagai format BSON), membuat integrasi data dalam beberapa jenis aplikasi lebih mudah dan lebih cepat. Dirilis di bawah Server Side Public License, MongoDB adalah perangkat lunak bebas dan sumber terbuka.<br><br>
    Kelebihan MongoDB
    - Performa yang lebih cepat<br>
        Kecepatan menjadi salah satu kelebihan dari MongoDB. Hal itu disebabkan dokumen database ini menyimpan sebagian besar datanya dalam RAM. Dengan begitu, kinerja akan lebih cepat saat sedang menjalankan kueri. Karena itu, penting untuk memiliki sistem dengan RAM dan indeks yang akurat untuk meningkatkan kinerja.
    - Sederhana<br>
        Tak hanya memiliki performa yang lebih cepat, MongoDB juga unggul karena kesederhanaan yang ditawarkannya. MongoDB menggunakan sintaks kueri yang simple sehingga lebih mudah dipahami daripada SQL. Selain itu, mulai dari proses penginstalan hingga eksekusi jauh lebih mudah dan cepat. Karena itu, MongoDB lebih disukai pemula karena kemudahan yang dimilikinya.
    - Fleksibilitas<br>
        Menurut KnowledgeNile, skema MongoDB tidak ditentukan. Artinya, program database tersebut memiliki arsitektur skema yang dinamis untuk penyimpanan data yang tidak terstruktur. Fleksibilitas dari MongoDB sangat diperlukan apalagi saat ini dunia data berkembang sangat cepat. Dengan menggunakan program database yang fleksibel tentunya sangat bermanfaat karena lebih mudah beradaptasi dengan perubahan.
    - Skalabilitas<br>
        Skalabilitas disebut menjadi salah satu kelebihan utama yang dimiliki oleh MongoDB. Pasalnya, MongoDB menggunakan skalabilitas horizontal yang membuatnya lebih mudah untuk meningkatkan kapasitas penyimpanan. Berbeda dengan database SQL yang menggunakan skalabilitas vertikal yang memerlukan penyimpanan lebih besar. Saat kebutuhan data meningkat, pengguna MongoDB dapat menambah cloud untuk meningkatkan kapasitas penyimpanan. Sebaliknya, untuk database SQL diperlukan hardware baru dengan spesifikasi yang lebih tinggi untuk meningkatkan kapasitas penyimpanan.
    
    Kekurangan MongoDB
    - Tidak mendukung transaksi<br>
        Transaksi mengacu pada proses meninjau dan menghilangkan data yang tidak diinginkan. MongoDB menggunakan transaksi ACIS (Atomicity, Consistency, Isolation, and Durability) yang tidak memerlukan transaksi. Namun, jika kamu membutuhkan transaksi untuk memperbarui dokumen, MongoDB tidak dapat diandalkan karena berpotensi terdapat kerusakan data.
    - Menggunakan banyak memori<br>
        Salah satu kekurangan terbesar dari MongoDB menurut GeeksforGeeks adalah penggunaan memori yang tinggi. Memang program database yang satu ini membutuhkan penyimpanan dengan jumlah yang besar karena kurangnya fungsionalitas yang menyebabkan duplikasi data. Data yang terduplikasi tersebut akan memakan banyak ruang di memori sehingga cepat penuh.
    - Ukuran data yang terbatas<br>
        Kekurangan selanjutnya dari MongoDB yang satu ini sering membuat penggunanya kerepotan. Pasalnya, ukuran data yang bisa digunakan hanya dibatasi sebesar 16 MB dalam setiap dokumennya. Selain itu, performa nesting untuk dokumen juga dibatasi hanya 100 per levelnya.
    - Masalah dalam pengindeksan<br>
        MongoDB memang menawarkan kinerja dengan kecepatan yang tinggi. Namun, hal itu bisa terjadi jika indeks yang dilakukan tepat. Melansir dari Virtual-DBA, saat indeks yang diimplementasikan kurang tepat, maka performa MongoDB akan berjalan lambat. Memperbaiki kesalahan dalam indeks juga memakan waktu, sehingga masalah dalam pengindeksan ini juga menjadi kekurangan dari MongoDB.
        
4. Postgre SQL<br><br><img src= "https://niagaspace.sgp1.digitaloceanspaces.com/blog/wp-content/uploads/2021/10/27194447/postgresql-adalah-1024x428.png" style="height:90px;width:auto"><br><br>
    PostgreSQL adalah sebuah sistem basis data yang disebarluaskan secara bebas menurut Perjanjian lisensi BSD. Peranti lunak ini merupakan salah satu basis data yang paling banyak digunakan saat ini, selain MySQL dan Oracle. PostgreSQL menyediakan fitur yang berguna untuk replikasi basis data. Fitur-fitur yang disediakan PostgreSQL antara lain DB Mirror, PGPool, Slony, PGCluster, dan lain-lain.<br><br>
     Kelebihan Postgre SQL
     - Dengan menggunakan PostgreSQL, tidak ada seorangpun dapat menuntut untuk pelanggaran terhadap perjanjian lisensi, sebagaimana tidak ada biaya lisensi yang diasosiasikan (digabungkan) untuk software. Hal ini menyebabkan PostgreSQL memberikan keuntungan tambahan, antara lain: bisnis menjadi lebih profitable dengan skala penyebaran yang luas. tidak ada kemungkinan diperiksa untuk pemenuhan lisensi, fleksibel untuk menjalankan konsep penelitian dan trial deployment tanpa memerlukan biaya lisensi tambahan.
     - Menghemat biaya staffing karena telah didesain dan dibuat sedemikian rupa untuk mempunyai tingkat pemeliharaan dan kebutuhan yang lebih rendah.
     - Terpercaya dan stabil. (banyak perusahaan yang melaporkan bahwa PostgreSQL tidak pernah, bahkan sekalipun, mengalami crashed pada saat melakukan operasi dengan tingkat aktivitas yang tinggi)
     - Extensible, artinya tidak memerlukan biaya untuk perluasan. Menggunakan penyimpanan data dengan banyak baris (multiple rows) yang dinamakan MVCC. Hal ini dimaksudkan agar PostgreSQL sangat responsif pada high volume environments.
     - Kaya akan fitur.
     
     Kekurangan Postgre SQL
     - Kurang cocok bekerja di lingkungan web jika dibandingkan dengan MySQL.
     - Kurang fokus dalam hal kelangsingan dan kecepatan.
     - Arsitektur dengan multiprose sulit diterapkan ke Windows, sebab Windows sangat thread-oriented. Saat ini bisa dijalankan di Windows, tapi melalui lapisan emulasi Cygwin.
     - Kurang unggul dalam hal ketersediaan fungsi built-in.
     - Replikasi di PostgreSQL belum disertakan dalam distribusi standarnya yang terbatas hanya bisa melakukan penambahan kolom, penggantian nama kolom, dan penggantian nama tabel.

5. SQLite<br><br><img src= "https://blog.desdelinux.net/wp-content/uploads/2020/05/Sqlite.jpeg" style="height:90px;width:auto"><br><br>
    SQLite merupakan sebuah sistem manajemen basisdata relasional yang bersifat ACID-compliant dan memiliki ukuran pustaka kode yang relatif kecil, ditulis dalam bahasa C. SQLite merupakan proyek yang bersifat public domain yang dikerjakan oleh D. Richard Hipp.<br><br>
     Kelebihan SQLite
     - Berbasis file<br>
        Seluruh database terdiri dari satu file pada disk, yang membuatnya sangat portabel.
     - Terstandarisasi dengan baik<br>
        Meskipun mungkin tampak seperti sebuah  implementasi DB yang "sederhana", SQLite menggunakan SQL yang tentunya kita sudah tahu bahwa SQL itu sudah sangat terstandar dengan baik.
     - Sangat baik untuk pengambangan dan bahkan pengujian<br>
        SQLite, dengan basis fitur yang kaya, dapat menawarkan lebih dari apa yang dibutuhkan untuk pembangunan dengan kesederhanaan bekerja dengan satu file dan terkait pustaka bahasa C.

     Kekurangan SQLite
     - Tidak ada manajemen pengguna<br>
        Database canggih datang dengan dukungan untuk pengguna, dikelola yaitu dengan koneksi hak akses set ke database dan tabel. Mengingat tujuan dan sifat SQLite (tidak digunakan untuk pengguna multi/banyak), fitur ini tidak ada.
     - Kurangnya kemungkinan untuk bekerja dengan kinerja tambahan<br>
        Sesuai dengan namanya SQLite mengutamakan kesederhanaan dan portabilitas, jadi SQLite tidak mungkin untuk bekerja dengan untuk mendapatkan banyak tambahan kinerja. Karena SQLite kesederhanaan, secara teknis tidak mungkin untuk membuatnya berkinerja lebih.

Dan masih banyak lagi jenis-jenis produk database, khusus di mata kuliah ini kita akan menggunakan Database MySQL

## 2. Install XAMPP
Sebenarnya untuk MySQL dan Apache kita dapat menginstallnya secara independen (terpisah), namun pada awal perkuliahan ini, untuk memudahkan dalam memahami materi, kita gunakan XAMPP terlebih dahulu, karena di dalamnya sudah termasuk beberapa sub-aplikasi yang kita perlukan, seperti Apache dan MySQL, dan berikut cara instalasinya : <br>
1. Download XAMPP terbaru<br>
    Silakan Download XAMPP terbaru untuk Windows di sini ([Download](https://downloadsapachefriends.global.ssl.fastly.net/8.1.1/xampp-windows-x64-8.1.1-2-VS16-installer.exe))
2. Buka file XAMPP yang baru saja diunduh<br>
    Kadang pada proses ini muncul pesan error. Jika ada, abaikan saja dan lanjutkan dengan klik YES dan OK.<br><img src="https://webhostmu.com/media/image-19.png"><br><img src="https://webhostmu.com/media/image-20.png">
3. Klik Next pada jendela installer<br>
    Pada tahapan ini seringkali muncul jendela yang isinya meminta Anda menutup semua aplikasi yang sedang berjalan. Jika semua aplikasi sudah ditutup, maka klik tombol Next.<br><img src="https://webhostmu.com/media/image-21.png">
4. Pilih sub-aplikasi yang ingin di install<br>
    Pada tahapan ini, Anda akan diminta untuk memilih sub-aplikasi yang mau diinstal. Centang saja semua pilihan dan klik tombol Next.<br><img src="https://webhostmu.com/media/image-22.png">
5. Pilih folder instalasi<br>
    Pastikan kapasitas hardisk atau drive tempat Xampp mau di install masih tersedia kuota yang mencukupi.<br><img src="https://webhostmu.com/media/image-23.png">
6. Pilih bahasa<br>
    Gunakan bahasa yang Anda familiar dengannya, kemudian klik Next.<br><img src="https://webhostmu.com/media/image-24.png">
7. Jalankan instalasi<br>
    Klik Next jika Anda sudah siap memulai proses instalasi Xampp.<br><img src="https://webhostmu.com/media/image-25.png">
8. Tunggu proses instalasi selesai<br>
    Proses Instalasi mungkin memakan waktu beberapa menit.<br><img src="https://webhostmu.com/media/image-26.png">
9. Start XAMPP<br>
    Jika sudah muncul jendela seperti di bawah ini, klik tombol Finish untuk menyelesaikannya. Selain itu, akan muncul opsi apakah Anda mau langsung menjalankan aplikasi XAMPP atau tidak. Jika ya, maka centang opsi tersebut.<br><img src="https://webhostmu.com/media/image-27.png">
10. Cara Menjalankan Aplikasi XAMPP<br>
    Bukalah aplikasi XAMPP, bisa melalui Start Menu atau Desktop, dan klik icon XAMPP.<br><br>
    Atau, jika Anda ingin membukanya langsung begitu proses instalasi selesai, maka centang kotak “Do you want to start the Control Panel now?” seperti terlihat pada gambar no. #9 di atas.<br><br>
    Setelah terbuka, silahkan klik tombol Start pada kolom Action sehingga tombol tersebut berubah menjadi Stop. Dengan mengklik tombol tersebut, artinya itulah aplikasi yang dijalankan. Biasanya jika saya menggunakan XAMPP, yang saya start hanyalah aplikasi Apache dan MySQL, karena saya tidak memerlukan aplikasi seperti Filezilla, dan lain-lain.<br><img src="https://webhostmu.com/media/image-28.png"><br><img src="https://webhostmu.com/media/image-29.png"><br>
    Sekarang bukalah browser kesukaan Anda, dan coba ketikkan http://localhost/ di address bar. Jika muncul tampilan seperti gambar di bawah ini, instalasi telah berhasil.<br><img src="https://webhostmu.com/media/image-30.png">
11. Jika Anda mengalami kesulitan di dalam menjalankan XAMPP seperti Apache XAMPP tidak bisa berjalan, mungkin bisa membaca artikel ini: [Mengatasi Error pada XAMPP](https://webhostmu.com/apache-tidak-bisa-running-di-xampp/)

## 3. Query Sederhana
Selanjutnya cobalah untuk masuk ke halaman ```localhost/phpmyadmin``` Jika diminta username dan password maka masukkan username root dan password dapat dikosongkan (default)<br><br><img src= "https://niagaspace.sgp1.digitaloceanspaces.com/blog/wp-content/uploads/2021/09/28205823/mysql-phpmyadmin-5-1536x796.png" style="height:800px;width:auto"><br><br>
Pada halaman inilah, Anda dapat melakukan pengelolaan database untuk website Anda. Misalnya, membuat database, mengedit, menghapus, bahkan melakukan query data.
### A. Membuat Database
### B. Membuat Tabel
### C. Query Sederhana
## 4. Generate Big Data
## 5. Query Nilai Siswa dari Big Data
## Referensi
https://idcloudhost.com/kamus-hosting/query/ <br>
https://www.dicoding.com/blog/apa-itu-database/ <br>
https://catatanshand.blogspot.com/2018/01/pengertian-fungsi-dan-macam-macam-jenis-database.html <br>
http://belajarlazarus.blogspot.com/2016/08/inilah-kelebihan-dan-kekurangan-sqlite.html <br>
https://glints.com/id/lowongan/kelebihan-kekurangan-mongodb/#.YeLNQfgxVPY <br>
https://webhostmu.com/cara-install-xampp/ <br>
