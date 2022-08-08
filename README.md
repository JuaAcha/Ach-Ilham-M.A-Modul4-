###### Nama : Ach Ilham M.A
###### Kelas : XII RPL 1
######  NO Absen : 03

## MODUL 4
### View Blade Template (php)
>Tugas 1 Membuat view pada project Anda

## Langkah 1

Nama folder yang akan Kita buat
- barang
- kategori
- layout

File yang dibuat
- home.blade.php (barang)
- index.blade.php (kategori)
- app.blade.php (layout)

## Langkah 2

Buat file dalam folder masing-masing sesuai gambar seperti di bawah ini

>![image](https://user-images.githubusercontent.com/109930502/183358694-61b96bfc-ae13-4a53-bcb2-77934f02a30f.png)

>Tugas 2 Membuat layout dengan master template blade untuk project anda

Pada file `app.blade.php` di dalam folder (layout) kita bisa mengambil **css dan JS di bootstrap** untuk mempermudah kita saat mengoding syntax, untuk bootstrap kalian bisa langsung ke link yang di bawah ini ya.
[Bootstrap](https://getbootstrap.com/docs/5.2/getting-started/introduction/#cdn-links)

![image](https://user-images.githubusercontent.com/109930502/183364884-748c147e-3d9c-43c3-9e9a-05597769d8fd.png)

Gambar diatas adalah bootstrap yang akan kita pakai pada codingan ini dengan mengambil css dan JS nya. untuk syntax seperti berikut ya
```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/css/bootstrap.min.css">
```

untuk JS nya juga inputkan kedalam file `app.blade.php` ya
```
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/js/bootstrap.bundle.min.js">
```

Selanjutnya isi file  `app.blade.php` seperti berikut
```
<!DDOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/css/bootstrap.min.css">
        <title>
            @yield('title')
</title>
</head>
<body>
    
<div class="container">
<nav class="navbar navbar-expand-lg bg-dark">
  <div class="container-fluid">
    <a class="navbar-brand text-white" href="#">Joki Jua</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link text-white" aria-current="page" href="/">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link text-white" href="/kategori">Kategori</a>
        </li>
        <li class="nav-item">
            <a class="nav-link text-white" href="/barang">List Joki</a>
</li>
    </div>
  </div>
</nav>
  </div>

  <div class="container">
    @yield('content')
</div>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/js/bootstrap.bundle.min.js">
    </script>
    </body>
    </html>
```

Selanjutnya hubungkan antara file `app.blade.php` dengan file `home.blade.php` dan `index.blade.php`. Untuk source codenya seperti dibawah ini

`home.blade.php`
```
@extends('layout.app')

@section('title')
    Barang
@endsection

@section('content')
<div class="mt-3">
   <table class="table table-striped">
    <thead>
        <tr>
            <th width="5%">No</th>
            <th>Choose Your Rank</th>
            <th width="15%">Select</th>
            <th width="20%">Amount</th>
            <th width="15%">Jockey Price</th>
            <th width="15%">Enter Quantity</th>
</tr>
</thead>

<tbody>
    <tr>
        <td>1</td>
        <td>Joki Grand Master</td>
        <td>per bintang</td>
        <td>1 bintang</td>
        <td>5000</td>
        <td>Tambah | Hapus</td>
</tr>
</tbody>

<tbody>
    <tr>
        <td>1</td>
        <td>Joki Epic</td>
        <td>per bintang</td>
        <td>1 bintang</td>
        <td>7000</td>
        <td>Tambah | Hapus</td>
</tr>
</tbody>

<tbody>
    <tr>
        <td>1</td>
        <td>Joki Legend</td>
        <td>per bintang</td>
        <td>1 bintang</td>
        <td>10000</td>
        <td>Tambah | Hapus</td>
</tr>
</tbody>

<tbody>
    <tr>
        <td>2</td>
        <td>Joki Mythic</td>
        <td>Per Point+Win</td>
        <td>10 point</td>
        <td>20000</td>
        <td>Tambah | Hapus</td>
</tr>
</tbody>

<tbody>
    <tr>
        <td>2</td>
        <td>Joki Mythic Glory 600+ s/d 1000+</td>
        <td>Per Point+Win</td>
        <td>10 point</td>
        <td>30000</td>
        <td>Tambah | Hapus</td>
</tr>
</tbody>
</table>
   </div>
@endsection
```

`index.blade.php`
```
@extends('layout.app')

@section('title')
    Kategori
@endsection

@section('content')
   <div class="mt-3">
   <table class="table table-striped">
    <thead>
        <tr>
            <th width="5%">N0</th>
            <th>Nama</th>
            <th width="15%">Aksi</th>
</tr>
</thead>

<tbody>
    <tr>
        <td>ATK</td>
        <td>Computer</td>
        <td>Accessories</td>
</tr>
</tbody>
</table>
   </div>
@endsection
```

Setelah itu cek hasil source codenya di sini `http://127.0.0.1:8000/barang`

![image](https://user-images.githubusercontent.com/109930502/183367760-b0a26981-781f-4a8d-a12f-091cd97447b5.png)

![image](https://user-images.githubusercontent.com/109930502/183368244-6b3e7ee3-ed91-4bde-ac32-14d8ae01eb1e.png)

