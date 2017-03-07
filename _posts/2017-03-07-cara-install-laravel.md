---
layout: post
title: "Cara Install Laravel"
date: "2017-03-07 14:10:00"
image: "/img/"
description: "Berbagai cara menginstall Laravel"
tags: Laravel, install, pemula
categories: Laravel
author: nafiesL
---
Bagi seorang developer yang terbiasa dengan "tinggal download" saat menginstall sebuah framework,
menginstall Laravel mungkin menjadi "agak merepotkan", karena:

-  **Harus terhubung Internet**. Secara *default*, Laravel tidak menyediakan file ZIP yang "tinggal download" dan "tinggal extract" untuk memulai sebuah project baru.
-  **Menggunakan Composer**. Setiap kali menginstall Laravel baru, kita harus memiliki Composer untuk menginstall Laravel dan dependensinya.

Baik, ada beberapa cara mengintall framework Laravel untuk project baru:
1.  Menggunakan 'composer create-project'
2.  Menggunakan Laravel Installer
3.  Mendownload Source Rilis Terbaru Laravel
4.  Mendownload Source dari Github Release Laravel

Pada ke-empat cara tersebut, semuanya tetap memerlukan **[Composer](https://getcomposer.org)** dan **internet** untuk menginstall framework Laravel hingga dapat memulai project.

Ingat untuk menjalankan langkah-langkah install framework Laravel, composer sudah harus terinstall pada PC teman-teman, jika belum ada composer, silakan [install dulu](https://getcomposer.org/download).
Jika teman-teman belum tau apa itu Composer, silakan baca [pengenalan composer](https://naflut.wordpress.com/2017/02/01/pengenalan-composer-analogi-dependency/)
dan [cara kerja composer](https://naflut.wordpress.com/2017/02/16/cara-kerja-composer-dan-lumbung-paket-packagist-org/).


Baik, Kita bahas satu persatu.

> Oh ya, pastikan semua perintah terminal yang kita lakukan berada pada direktori web localhost kita  
    (misal: **C:\\xampp\htdocs**, atau **/var/www/html**)

## Menggunakan 'composer create-project'

Untuk menginstall Framework Laravel menggunakan **composer create-project**, lakukan langkah-langkah berikut:
1. Berikan perintah berikut pada terminal :  
`$ composer create-project Laravel/Laravel nama-direktori-project`
2. Tunggu hingga proses installasi selesai.
> Durasi proses ini bergantung pada kecepatan koneksi internet yang kita gunakan.
3. Setelah proses selesai, kita masuk ke direktori **nama-direktori-project**  
`$ cd nama-direktori-project`
4. Untuk memeriksa apakah Laravel terinstall dengan benar, coba perintah berikut:  
`$ php artisan -V`
5. Jika instalasi berjalan normal, maka akan muncul informasi `Laravel Framework 5.4.15` *(Versi terbaru saat artikel ini ditulis)*.

Oke, cara pertama selesai. Kita masuk cara keduanya.

## Menggunakan Laravel Installer
Untuk dapat menginstall Laravel dengan cara ini, kita akan menginstall sebuah paket dari composer yang bernama **Laravel/installer** pada PC atau laptop kita.

1. Dengan menggunakan terminal, berikan perintah berikut:  
`$ composer global require "Laravel/installer"`
> Dengan perintah ini, composer akan mendownload paket **Laravel/installer** secara global dalam PC kita, karena paket ini akan kita gunakan dengan terminal.
2. Baik setelah selesai, kita harus menambahkan sebuah script **export PATH** pada file `~/.bashrc` *(di sini kebetulan saya menggunakan Ubuntu)*.
Tambahkan script berikut pada akhir isi file:  
`export PATH="$PATH:$HOME/.composer/vendor/bin"`  
3. Simpan dan exit.
4. Pada terminal, berikan perintah berikut :
`$ source ~/.bashrc`
5. Jika tahap ini dijalankan dengan benar, seharusnya ketika kita berikan perintah berikut ke terminal :  
`$ laravel -V`  
Akan menghasilkan informasi versi Laravel Installer :  
`Laravel Installer version 1.3.3` *(versi terbaru saat artikel ini dibuat)*.

Oke dengan adanya **Laravel Installer**, untuk menginstall project Laravel baru.
1. Kita bisa berikan perintah:  
`laravel new nama-direktori-project` *(proses installasi laravel akan berjalan)*
2. Ketika proses instalasi selesai, maka kita dapat **cd** ke **nama-direktori-project**, dan memberikan perintah :  
`php artisan -V`
3. Jika proses installasi berjalan dengan baik, perintah tersebut akan menghasilkan :  
`Laravel Framework 5.4.15`

Artinya cara install Laravel yang kedua sudah selesai. Sekarang kita lihat cara yang ketiga.

## Mendownload Source Rilis Terbaru Laravel
Cara menginstall Laravel yang ketiga adalah dengan mendownload source code rilis terbaru framework Laravel.

1. Download source framework Laravel dari url berikut:  
`http://cabinet.Laravel.com/latest.zip` atau [klik disini](http://cabinet.Laravel.com/latest.zip).  
Kita akan mendapatkan file `latest.zip`.  
2. Pindahkan file tersebut ke dalam direktori project kita, kemudian **extract** ke direktori **nama-direktori-project**.
3. Pada terminal, **cd** ke **nama-direktori-project**, kemudian berikan perintah pada terminal :  
    `composer install`

    Tunggu proses installasi hingga selesai.

    > Pada langkah ini, proses installasi oleh composer cenderung lebih cepat, karena pada direktori project kita sudah ada file **composer.lock**.
    Sehingga composer tinggal menginstall seluruh paket yang ada pada file tersebut.

4. Oke, proses instalasi oleh composer selesai, maka kita dapat langsung mencoba perintah :  
`php artisan -V`  
Dan menghasilkan :  
`Laravel Framework 5.4.15`

Yah, walaupun awalnya kita "mengambil source" framework ini dengan cara men-download, kita tetap harus **menggunakan composer** juga untuk menginstall paket-paket dependensinya.

Oke, selanjutnya kita bahas cara keempat

## Mendownload Source dari Github Laravel

Untuk cara install yang ini, berikut tahap instalasinya :
1. Kunjungi halaman github dari Laravel **[https://github.com/Laravel/Laravel](https://github.com/Laravel/Laravel)**
2. Klik link `releases` atau [https://github.com/Laravel/Laravel/releases](https://github.com/Laravel/Laravel/releases)
3. Klik icon/link `zip` pada rilis versi terbaru Laravel untuk mendownload source code dengan format ZIP
4. **Extract** file zip tersebut pada direktori web project kita, misal ke direktori **nama-direktori-project**.
5. Buka terminal, kemudian `cd nama-direktori-project`
6. Kemudian berikan perintah pada terminal :  
`composer install` Tunggu hingga proses installasi selesai
7. Setelah proses instalasi oleh composer selesai, kita coba perintah :  
`php artisan -V`
8. Seharusnya muncul informasi : `Laravel Framework 5.4.15`

## Simpulan

Baik sudah kita bahas ada 4 cara menginstall framework Laravel. Masing-masing memiliki kelebihan dan kekurangan:

1.  Menggunakan 'composer create-project'
    > Kelebihan:
    > - Cukup satu perintah terminal
    > - Dapat menentukan versi laravel mana yang ingin digunakan/di-download
    > 
    > Kekurangan:
    > - Terkadang proses cukup lama, memakan waktu beberapa menit.

2.  Menggunakan Laravel Installer
    > Kelebihan:
    > - Cukup satu perintah terminal
    > - Selalu men-download Laravel versi rilis terbaru
    > - Proses composer cenderung lebih cepat dari cara pertama
    > 
    > Kekurangan:
    > - Perlu pengaturan awal sebelum mulai digunakan

3.  Mendownload Source Rilis Terbaru Laravel
    > Kelebihan:
    > - Proses composer cenderung lebih cepat dari cara pertama (karena sudah ada file **composer.lock**)
    > 
    > Kekurangan:
    > - Agak repot mendownload, dan extract ke direktori project

4.  Mendownload Source dari Github Release Laravel
    > Kelebihan:
    > - Tidak ada
    > 
    > Kekurangan:
    > - Agak repot mendownload, dan extract ke direktori project

Sebenarnya untuk menginstall laravel pada project baru, kita dapat menduplikat direktori dari project yang lama,
selama paket-paket dependensi yang digunakan sudah sesuai (sama dengan project sebelumnya), maka ini bisa menjadi salah satu solusi.