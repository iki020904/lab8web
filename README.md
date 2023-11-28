# Lab8web

Nama : Muhammad Rifqi aziz

NIM  : 312210111

Kelas : TI.22.A1

## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|Instruksi Praktikum|[Click Here](#instruksi-praktikum)|
|2|Langkah-langkah Praktikum|[Click Here](#langkah-langkah-praktikum)|
|3|Result|[Click Here](#result)|

## Instruksi Praktikum
1. Persiapkan text editor misalnya VSCode.
2. Buat folder baru dengan nama lab8_php_database pada docroot webserver (htdocs)
3. Ikuti langkah-langkah praktikum yang akan dijelaskan berikutnya.

## Langkah-langkah Praktikum
1. Persiapan Untuk memulai membuat aplikasi CRUD sederhana, yang perlu disiapkan adalah database server menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan melalui XAMPP.

2. Menjalankan MySQL Server Untuk menjalankan MySQL Server dari menu XAMPP Control.

3. Membuat Database: Studi Kasus Data Barang
```
CREATE DATABASE latihan1;
```
```
CREATE TABLE data_barang (
    id_barang int(10) auto_increment Primary Key,
    kategori varchar(30),
    nama varchar(30),
    gambar varchar(100),
    harga_beli decimal(10,0),
    harga_jual decimal(10,0),
    stok int(4)
);
```

![Screenshot (158)](https://github.com/syifaaurellia/Lab8web/assets/115867244/5b60a65b-853a-45c4-a666-81c9999ccc10)


4. Menambah Data
```
INSERT INTO data_barang (kategori, nama, gambar, harga_beli, harga_jual, stok)
VALUES ('Elektronik', 'HP Samsung Android', 'hp_samsung.jpg', 2000000, 2400000, 5),
('Elektronik', 'HP Xiaomi Android', 'hp_xiaomi.jpg', 1000000, 1400000, 5),
('Elektronik', 'HP OPPO Android', 'hp_oppo.jpg', 1800000, 2300000, 5);
```

![Screenshot (150)](https://github.com/syifaaurellia/Lab8web/assets/115867244/db3281b0-e06c-4461-98e6-33821fedf087)


5. Membuat Program CRUD, Buat folder lab8_php_database pada root directory web server (d:\xampp\htdocs)

6. Membuat file koneksi database, Buat file baru dengan nama `koneksi.php`
```
<?php
$host = "localhost";
$user = "root";
$pass = "";
$db = "latihan1";
$conn = mysqli_connect($host, $user, $pass, $db);
if ($conn == false)
{
    echo "Koneksi ke server gagal.";
    die();
} #else echo "Koneksi berhasil";
?>
```

> Buka melalui browser untuk menguji koneksi database untuk menyampilkan pesan koneksi berhasil, ***uncomment*** pada perintah echo “koneksi berhasil”;

![Screenshot (151)](https://github.com/syifaaurellia/Lab8web/assets/115867244/012e0941-ef81-47b8-9bad-5c787a740ab6)


7. Membuat file index untuk menampilkan data (Read), buat file baru dengan nama `index.php`

> **Akses File-->>**[index.php](index.php)

![data barang](https://github.com/iki020904/lab8web/assets/115804283/37643c02-e077-48b6-93ae-bdc675120ee9)


8. Menambah Data (Create), buat file baru dengan nama `tambah.php`

> **Akses File-->>**[tambah.php](tambah.php)

![tambah barang](https://github.com/iki020904/lab8web/assets/115804283/754f4575-9636-4f8b-a767-0e6c2203b409)



9. Mengubah Data (Update), buat file baru dengan nama `ubah.php`

> **Akses File-->>**[ubah.php](ubah.php)

![ubah ](https://github.com/iki020904/lab8web/assets/115804283/51301e9e-5d89-4b2d-bc49-903ccbeefdfa)


10. Menghapus Data (Delete), buat file baru dengan nama `hapus.php`
```
<?php
include_once 'koneksi.php';
$id = $_GET['id'];
$sql = "DELETE FROM data_barang WHERE id_barang = '{$id}'";
$result = mysqli_query($conn, $sql);
header('location: index.php');
>
```

## Result



![data barang](https://github.com/iki020904/lab8web/assets/115804283/8546e4da-6d22-43de-955b-100b4294ea4f)



## Finish, Terima kasih
