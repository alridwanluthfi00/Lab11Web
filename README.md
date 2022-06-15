# Lab11Web

## Nama     : Luthfi Al Ridwan
## NIM      : 312010112
## Kelas    : TI.20.A.1
## Matkul   : Pemrograman Web

## Sebelum memulai menggunakan Framework Codeigniter, perlu dilakukan konfigurasi pada webserver. Beberapa ekstensi PHP perlu diaktifkan untuk kebutuhan pengembangan Codeigniter 4.
Berikut beberapa ekstensi yang perlu diaktifkan:
- php-json ekstension untuk bekerja dengan JSON;
- php-mysqlnd native driver untuk MySQL;
- php-xml ekstension untuk bekerja dengan XML;
- php-intl ekstensi untuk membuat aplikasi multibahasa;
- libcurl ( opsional ) jika ingin pakai curl.

![ss1](https://user-images.githubusercontent.com/73066008/173904282-6ca59718-c26f-4d21-980c-73f20143df74.png)

## Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.

![ss2](https://user-images.githubusercontent.com/73066008/173904342-2b97be97-dd43-4b64-a8fd-c49b98307919.png)

# Instalasi Codeigniter 4
## Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual.
Unduh Codeigniter dari website https://codeigniter.com/download
- Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.
- Ubah nama direktory framework-4.x.xx menjadi ci4.
- Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/

![ss3](https://user-images.githubusercontent.com/73066008/173904378-fcc65fcd-d93b-4be4-8e20-3b5967b27ad8.png)

## Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable CI_ENVIRONMENT menjadi development.

![ss4](https://user-images.githubusercontent.com/73066008/173904416-6ea3713c-53d4-4397-801c-6c29952b6e9c.png)

## Routing dan Controller 
Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk meudian oleh router tesebut diarahkan ke Controller. Router terletak pada file app/config/Routes.php

![ss5 (1)](https://user-images.githubusercontent.com/73066008/173909254-76d1ec24-c3c3-48e2-9d1a-64ad9e0b43f3.png)

## Membuat Route Baru
Tambahkan kode berikut di dalam Routes.php :

![ss5](https://user-images.githubusercontent.com/73066008/173904438-db96f6f0-6d9d-4a81-8679-e8a0daffb9dc.png)

## Membuat Controller
Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php pada direktori Controller kemudian isi kodenya seperti berikut :

![ss6](https://user-images.githubusercontent.com/73066008/173904644-2a1f64c2-70d3-4390-9ccb-c12e4578a04e.png)

## Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset 
css dan javascript terletak pada direktori public. Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.

![ss7](https://user-images.githubusercontent.com/73066008/173905123-d7df1fb5-300c-4863-b8ff-cab38622bacf.png)

Kemudian buat folder template pada direktori view kemudian buat file header.php dan footer.php
## File app/view/template/header.php

    <!DOCTYPE html>
    <html lang="en">
    <head>
     <meta charset="UTF-8">
     <title><?= $title; ?></title>
     <link rel="stylesheet" href="<?= base_url('/style.css');?>">
    </head>
    <body>
     <div id="container">
     <header>
     <h1>Layout Sederhana</h1>
     </header>
     <nav>
     <a href="<?= base_url('/');?>" class="active">Home</a>
     <a href="<?= base_url('/artikel');?>">Artikel</a>
     <a href="<?= base_url('/about');?>">About</a>
     <a href="<?= base_url('/contact');?>">Kontak</a>
     </nav>
     <section id="wrapper">
     <section id="main">
     
## File app/view/template/footer.php

    </section>
     <aside id="sidebar">
    <div class="widget-box">
     <h3 class="title">Widget Header</h3>
     <ul>
     <li><a href="#">Widget Link</a></li>
     <li><a href="#">Widget Link</a></li>
     </ul>
     </div>
     <div class="widget-box">
     <h3 class="title">Widget Text</h3>
     <p>Vestibulum lorem elit, iaculis in nisl volutpat, malesuada 
    tincidunt arcu. Proin in leo fringilla, vestibulum mi porta, faucibus felis. 
    Integer pharetra est nunc, nec pretium nunc pretium ac.</p>
     </div>
     </aside>
     </section>
     <footer>
     <p>&copy; 2021 - Universitas Pelita Bangsa</p>
     </footer>
     </div>
    </body>
    </html>

## Kemudian ubah file app/view/about.php seperti berikut :

    <?= $this->include('template/header'); ?>
    <h1><?= $title; ?></h1>
    <hr>
    <p><?= $content; ?></p>
    <?= $this->include('template/footer'); ?>

## Selanjutnya refresh tampilan browser

![ss8](https://user-images.githubusercontent.com/73066008/173905146-0148ce38-3648-4ca2-bc16-2552b4438348.png)





