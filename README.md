# lab7Web

# Praktikum 7: PHP Dasar

## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|Instruksi Praktikum |[Click Here](##InstruksiPraktikum)|
|2|Langkah-langkah Praktikum|[Click Here](##Langkah-langkahPraktikum)|
|3|Konfigurasi Web Server|[Click Here](##KonfigurasiWebServer)|
|4|Menjalankan Web Server|[Click Here](##MenjalankanWebServer)|
|5|Memulai PHP|[Click Here](##MemulaIPHP)|
|6|PHP Dasar|[Click Here](##PHPDasar)|
|7|Variable PHP|[Click Here](##VariablePHP)|
|8|Predefine Variable $_GET|[Click Here](##PredefineVariable$_GET)|
|9|Membuat Form Input|[Click Here](##MembuatFormInput)|
|10|Operator|[Click Here](##Operator)|
|11|Kondisi IF|[Click Here](##KondisiIF)|
|12|Kondisi Switch|[Click Here](##KondisiSwitch)|
|13|Perulangan for|[Click Here](##Perulanganfor)|
|14|Perulangan while|[Click Here](##Perulanganwhile)|
|15|Perulangan dowhile|[Click Here](##Perulangandowhile)|
|16|PERTANYAAN DAN TUGAS|[Click Here](##PERTANYAANDANTUGAS)|

## Instruksi Praktikum 
1. Persiapkan text editor misalnya VSCode.
2. Buat folder baru dengan nama lab7_php_dasar pada docroot webserver (htdocs)
3. Ikuti langkah-langkah praktikum yang akan dijelaskan berikutnya.

## Langkah-langkah Praktikum
### Persiapan
Untuk memulai membuat kode php, perlu disiapkan web server dan interpreter PHP
terlebih dahulu. Web servar yang kita gunakan adalah Apache 2 dan interpreter PHP 7.
Untuk memudahkan proses praktikum, kita gunakan aplikasi bundle web server yaitu
XAMPP.
### Install XAMPP
Unduh XAMPP dari https://www.apachefriends.org/download.html dan pilih versi
portable untuk memudahkan proses installasi. Kemudian extract file tersebut, seusikan
direktorinya (misal: d:\xampp).

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/98a81bc0-8af4-449c-a21f-c034e99a553b)

## Konfigurasi Web Server
### • Konfigurasi Apache
Untuk konfigurasi HTTP server, seperti port yang digunakan akses HTTP, modul
yang diaktifkan, lokasi document root, dll.
Lokasi file: \xampp\apache\conf\httpd.conf
### • Konfigrasi PHP
Untuk konfigurasi perilaku engine PHP yang berefek pada keamanan dan performa.
Seperti batas maksimal waktu eksekusi script, batas file yang dapat diupload, error
reporting, dll.
Lokasi file: \xampp\php\php.ini
### • Konfigrasi MySql
Konfigurasi server MySQL, seperti administrator user, port, timezone, dll.
Lokasi file: \xampp\mysql\bin\my.ini

## Menjalankan Web Server
Untuk menjalankan web server dari menu XAMPP Control.

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/59a66bf5-8d79-41c1-bdf8-dece9296077d)

### • Uji coba apakah server sudah berkerja dengan baik
http://127.0.0.1 atau http://localhost
Tampil halaman utama XAMPP jika server sudah berkerja dengan baik.
### • Dokumen Website
Semua file website tempatkan di direktori: \xampp\htdocs\
### • Database MySQL
Direktori: \xampp\mysql\
Manajemen database: http://localhost/phpmyadmin

## Memulai PHP
Buat folder lab7_php_dasar pada root directory web server (d:\xampp\htdocs)

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/3e8759b3-4c77-4b0d-9ab5-b4d25ee12b96)

Kemudian untuk mengakses direktory tersebut pada web server dengan mengakses URL:
http://localhost/lab7_php_dasar/

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/78c32c2b-0e83-47ea-b8b8-99ce0e706c8d)

## PHP Dasar
Buat file baru dengan nama php_dasar.php pada directory tersebut. Kemudian buat
kode seperti berikut.

```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>PHP Dasar</title>
</head>
<body>
<h1>Belajar PHP Dasar</h1>
<?php
echo "Hello World";
?>
</body>
</html>
```
Kemudian untuk mengakses hasilnya melalui URL:
http://localhost/lab7_php_dasar/php_dasar.php

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/a4005454-860c-4735-af50-192e3c2e7566)

## Variable PHP
Menambahkan variable pada program.

```
<?php
$nim = "0411500400";
$nama = 'Abdullah';
echo "NIM : " . $nim . "<br>";
echo "Nama : $nama";
?>
```

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/57ab5327-a3ab-4bf5-9fca-4788d331530e)

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/d8a2d648-c054-4a12-b621-49441a774b06)

## Predefine Variable $_GET

```
<?php
echo 'Selamat Datang ' . $_GET['nama'];
?>
```
Untuk mengaksesnya gunakan URL:
http://localhost/lab7_php_dasar/latihan2.php?nama=Rani

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/b3383781-3e81-4ecd-9f2b-a6090a171a58)

## Membuat Form Input
```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>PHP Dasar</title>
</head>
<body>
<h2>Form Input</h2>
<form method="post">
<label>Nama: </label>
<input type="text" name="nama">
<input type="submit" value="Kirim">
</form>
<?php
echo 'Selamat Datang ' . $_POST['nama'];
?>
</body>
</html>
```

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/e48a6150-22e5-4a5f-921f-5ff78c5ffb9d)

## Operator

```
<?php
$gaji = 1000000;
$pajak = 0.1;
$thp = $gaji - ($gaji*$pajak);
echo "Gaji sebelum pajak = Rp. $gaji <br>";
echo "Gaji yang dibawa pulang = Rp. $thp";
?>
```

### Penjelasan

#### 1. Inisialisasi Variabel:
   
    • $gaji = 1000000; --> Menetapkan gaji sebelum pajak sebesar Rp. 1.000.000.

    • $pajak = 0.1; --> Menetapkan persentase pajak sebesar 10%.

#### 2.  Perhitungan Gaji Bersih:
   
    • $thp = $gaji - ($gaji * $pajak); --> Menghitung gaji bersih (Take-Home Pay/THP) dengan mengurangkan pajak dari gaji.

#### 3. Menampilkan Hasil:

    • echo "Gaji sebelum pajak = Rp. $gaji <br>"; --> Menampilkan gaji sebelum pajak.

    • echo "Gaji yang dibawa pulang = Rp. $thp"; --> Menampilkan gaji bersih yang dibawa pulang setelah dipotong pajak.

#### Jadi, hasil akhirnya adalah program akan menampilkan dua baris teks:

    • "Gaji sebelum pajak = Rp. 1.000.000"

    • "Gaji yang dibawa pulang = Rp. (nilai gaji setelah dipotong pajak)"

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/ebbf7204-b285-4e8c-ab84-fe2e6116ae0a)

## Kondisi IF

```
<?php
$nama_hari = date("l");
if ($nama_hari == "Sunday") {
echo "Minggu";
} elseif ($nama_hari == "Monday") {
echo "Senin";
} else {
echo "Selasa";
}
?>
```

### Penjelasan

#### 1. Mendapatkan Nama Hari:

    • $nama_hari = date("l"); --> Menggunakan fungsi date("l") untuk mendapatkan nama hari saat ini dan menyimpannya dalam variabel $nama_hari.
    
#### 2. Pengecekan Nama Hari:

    • if ($nama_hari == "Sunday") { echo "Minggu"; } --> Jika hari saat ini adalah Minggu, maka program akan menampilkan "Minggu".
    
    • elseif ($nama_hari == "Monday") { echo "Senin"; } --> Jika hari saat ini adalah Senin, maka program akan menampilkan "Senin".
    
    • else { echo "Selasa"; } --> Jika hari saat ini bukan Minggu atau Senin, maka program akan menampilkan "Selasa".
    
Jadi, jika Anda menjalankan program ini pada hari Minggu, hasilnya akan "Minggu", jika pada hari Senin, hasilnya akan "Senin", dan untuk hari-hari selain Minggu dan Senin, hasilnya akan "Selasa".

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/c414d99d-90f2-4524-ac8d-5d1d9802f57e)

## Kondisi Switch

```
<?php
$nama_hari = date("l");
switch ($nama_hari) {
case "Sunday":
echo "Minggu";
break;
case "Monday":
echo "Senin";
break;
case "Tuesday":
echo "Selasa";
break;
default:
echo "Sabtu";
?>
```

### Penjelasan

#### 1. Mendapatkan Nama Hari:

    • $nama_hari = date("l"); --> Menggunakan fungsi date("l") untuk mendapatkan nama hari saat ini dan menyimpannya dalam variabel $nama_hari.

#### 2. Struktur Switch:

    • switch ($nama_hari) { --> Memulai struktur switch dengan variabel yang akan diperiksa ($nama_hari).
    
    • case "Sunday": echo "Minggu"; break; --> Jika nilai $nama_hari adalah "Sunday" (Minggu), program akan menampilkan "Minggu" dan kemudian keluar dari struktur switch.
    
    • case "Monday": echo "Senin"; break; --> Jika nilai $nama_hari adalah "Monday" (Senin), program akan menampilkan "Senin" dan keluar dari struktur switch.
    
    • case "Tuesday": echo "Selasa"; break; --> Jika nilai $nama_hari adalah "Tuesday" (Selasa), program akan menampilkan "Selasa" dan keluar dari struktur switch.
    
    • default: echo "Sabtu"; --> Jika nilai $nama_hari tidak cocok dengan kondisi di atas (yaitu, bukan Minggu, Senin, atau Selasa), program akan menampilkan "Sabtu".
    
Jadi, hasil akhirnya adalah program akan menampilkan nama hari sesuai dengan hari saat ini. Jika hari saat ini adalah Minggu, outputnya adalah "Minggu", jika Senin, outputnya adalah "Senin", jika Selasa, outputnya adalah "Selasa", dan untuk hari-hari lainnya, outputnya adalah "Sabtu".

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/99db15f6-68fc-445b-a51e-00f6817ba3ca)

## Perulangan for

```
<?php
echo "Perulangan 1 sampai 10 <br />";
for ($i=1; $i<=10; $i++) {
echo "Perulangan ke: " . $i . '<br />';
}
echo "Perulangan Menurun dari 10 ke 1 <br />";
for ($i=10; $i>=1; $i--) {
echo "Perulangan ke: " . $i . '<br />';
}
?>
```

### Penjelasan

#### 1. Perulangan Menaik (1 sampai 10):

    • for ($i=1; $i<=10; $i++) { --> Inisialisasi variabel $i dengan nilai awal 1, kemudian melakukan perulangan selama $i kurang dari atau sama dengan 10, dan setiap iterasi menambah nilai $i satu per satu.

    • echo "Perulangan ke: " . $i . '<br />'; --> Menampilkan pesan "Perulangan ke: [nilai $i]" di setiap iterasi. Ini akan menghasilkan pesan dari perulangan 1 sampai 10.

#### 2. Perulangan Menurun (dari 10 ke 1):

    • for ($i=10; $i>=1; $i--) { --> Inisialisasi variabel $i dengan nilai awal 10, kemudian melakukan perulangan selama $i lebih besar dari atau sama dengan 1, dan setiap iterasi mengurangkan nilai $i satu per satu.

    • echo "Perulangan ke: " . $i . '<br />'; --> Menampilkan pesan "Perulangan ke: [nilai $i]" di setiap iterasi. Ini akan menghasilkan pesan dari perulangan 10 sampai 1.

#### Jadi, hasil akhirnya adalah program akan menampilkan dua set pesan:

• Pesan perulangan dari 1 sampai 10.

• Pesan perulangan menurun dari 10 ke 1.

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/d0b55144-fc3c-4a80-869d-1262d15ac725)

## Perulangan while

```
<?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
while ($i<=10) {
echo "Perulangan ke: " . $i . '<br />';
$i++;
}
?>
```

### Penjelasan

#### 1. Inisialisasi Variabel:

    • $i = 1; --> Langkah pertama adalah memberi nilai awal 1 pada variabel $i. Ini digunakan sebagai penghitung perulangan.

#### 2. Perulangan dengan while:

    • while ($i <= 10) { --> Langkah kedua, kita menggunakan perulangan while dengan kondisi bahwa perulangan akan terus dilakukan selama nilai $i kurang dari atau sama dengan 10.

    • echo "Perulangan ke: " . $i . '<br />'; --> Langkah ketiga, di dalam perulangan, kita menampilkan pesan "Perulangan ke: [nilai $i]" pada setiap iterasi.

    • $i++; --> Langkah keempat, setiap kali iterasi selesai, nilai $i akan ditambah 1. Ini penting untuk mencegah perulangan tak terbatas.

#### Hasil:

Jadi, hasil akhirnya adalah program akan menampilkan pesan "Perulangan ke: [nilai $i]" dari 1 sampai 10. Setiap iterasi menambah nilai $i hingga mencapai 10, dan setelah itu, perulangan akan berhenti.

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/ad08a8c6-a0aa-4fef-9619-afa0fdfcf50b)

## Perulangan dowhile

```
<?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
do {
echo "Perulangan ke: " . $i . '<br />';
$i++;
} while ($i<=10);
?>
```

### Penjelasan

#### 1. Inisialisasi Variabel:

    • $i = 1; --> Langkah pertama adalah memberi nilai awal 1 pada variabel $i. Ini digunakan sebagai penghitung perulangan.

#### 2. Perulangan dengan do-while:

    • do { --> Langkah kedua, kita menggunakan perulangan do-while. Perbedaan utama dengan while biasa adalah bahwa pernyataan di dalam blok do akan dijalankan setidaknya satu kali sebelum kondisi di while diuji.

    • echo "Perulangan ke: " . $i . '<br />'; --> Langkah ketiga, di dalam perulangan, kita menampilkan pesan "Perulangan ke: [nilai $i]".

    • $i++; --> Langkah keempat, nilai $i ditambah 1 setelah menampilkan pesan, sehingga memastikan bahwa perulangan tidak akan berjalan tanpa batas.

#### 3. Kondisi while:

    • while ($i <= 10); --> Langkah kelima, kondisi while diuji setelah satu iterasi do-while. Jika nilai $i masih kurang dari atau sama dengan 10, perulangan akan terus berlanjut. Jika tidak, perulangan berhenti.
    
#### Hasil:

Jadi, hasil akhirnya adalah program akan menampilkan pesan "Perulangan ke: [nilai $i]" dari 1 sampai 10. Meskipun kondisi while diuji setelah blok do dijalankan, kita tetap memastikan bahwa setiap iterasi akan menambah nilai $i, sehingga perulangan tidak berjalan tanpa batas.

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/213c440f-b410-4975-ac5f-96c3c72754de)

## PERTANYAAN DAN TUGAS

Buatlah program PHP sederhana dengan menggunakan form input yang menampilkan
nama, tanggal lahir dan pekerjaan. Kemudian tampilkan outputnya dengan menghitung
umur berdasarkan inputan tanggal lahir. Dan pilihan pekerjaan dengan gaji yang
berbeda-beda sesuai pilihan pekerjaan.

### CODE:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Pekerjaan</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 400px;
            margin: 20px auto;
        }

        h2 {
            text-align: center;
        }

        form {
            text-align: left;
        }

        label {
            display: block;
            margin-top: 10px;
        }

        input,
        select {
            width: 100%;
            padding: 8px;
            margin-top: 5px;
        }

        input[type="submit"] {
            background-color: #4caf50;
            color: white;
            cursor: pointer;
        }

        .hasil {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h2>Form Pekerjaan</h2>

    <form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]); ?>">
        <label for="nama">Nama:</label>
        <input type="text" name="nama" required>

        <label for="tanggal_lahir">Tanggal Lahir:</label>
        <input type="date" name="tanggal_lahir" required>

        <label for="pekerjaan">Pekerjaan:</label>
        <select name="pekerjaan" required>
            <option value="Programmer">Programmer</option>
            <option value="Designer">Designer</option>
            <option value="Marketing">Marketing</option>
        </select>

        <input type="submit" value="Submit">
    </form>

    <?php
    // Memproses form setelah pengguna mengirimkan data
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        $nama = $_POST["nama"];
        $tanggal_lahir = $_POST["tanggal_lahir"];
        $pekerjaan = $_POST["pekerjaan"];

        // Menghitung umur berdasarkan tanggal lahir
        $umur = date_diff(date_create($tanggal_lahir), date_create('today'))->y;

        // Menentukan gaji berdasarkan pekerjaan
        switch ($pekerjaan) {
            case 'Programmer':
                $gaji = 5000000;
                break;
            case 'Designer':
                $gaji = 4500000;
                break;
            case 'Marketing':
                $gaji = 4000000;
                break;
            default:
                $gaji = 0; // Gaji default jika pekerjaan tidak dikenali
        }
    ?>
        <div class="hasil">
            <h3>Hasil Input:</h3>
            <p><strong>Nama:</strong> <?php echo $nama; ?></p>
            <p><strong>Tanggal Lahir:</strong> <?php echo $tanggal_lahir; ?></p>
            <p><strong>Umur:</strong> <?php echo $umur; ?> tahun</p>
            <p><strong>Pekerjaan:</strong> <?php echo $pekerjaan; ?></p>
            <p><strong>Gaji:</strong> Rp. <?php echo number_format($gaji, 0, ',', '.'); ?></p>
        </div>
    <?php
    }
    ?>
</body>
</html>
```

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/0f05f6fe-e7ad-4301-b714-b50ab5d03854)

### OUTPUT 

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/d867e2f8-b6b2-4c6d-892a-72c7b575c46d)

![image](https://github.com/Aliyahasmarani/lab7Web/assets/115197672/55e3f41b-dbcb-417c-ac8a-f0fc501b8bf4)
