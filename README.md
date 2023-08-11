# Investigate-Hotel-Business-using-Data-Visualization

**Tool :** Jupyter Notebook <br>
**Programming Language :** Python <br>
**Visualization :** Matplotlib, Seaborn <br>
**Dataset :** [Dataset](https://github.com/soniaepifanysandah/Investigate-Hotel-Business-using-Data-Visualization/blob/main/data/hotel_bookings_data.csv)

## Introduction
Pada project ini akan dilakukan analisa untuk mendapatkan insight-insight yang berhubungan dengan performa bisnis hotel. Insight tersebut akan dicari melalui eksplorasi data, seperti menganalisis bagaimana perilaku pelanggan dalam melakukan pemesanan tiket hotel ataupun mencari faktor-faktor yang mempengaruhi pembatalan pemesanan tiket hotel. Kemudian insight akan disajikan menggunakan visualisasi.

## Problem Statement
Melakukan investigasi terhadap performa bisnis hotel melalui jumlah pemesanan setiap bulan, hubungan durasi menginap terhadap pembatalan pemesanan, hubungan lead time pemesanan terhadap pembatalan pemesanan.

## Objective
Membuat visualisasi berbasis data sebagai insight bagi bisnis hotel

## Overview
Dataset terdiri dari 119390 baris dan 29 kolom dengan periode tahun 2017-2019.
<p align="center">
   <img src="picture/pic info data.png" width = 400 px alt="grafik1">
</p>

## Data Preprocessing
### 1. Mengatasi data null/missing values
- Terdapat missing values pada 4 feature, yaitu **company (94.307%), agent (13.686%), city (0.409%), children (0.003%)**
- Treatment : <br>
Kolom `children` akan diisi dengan `0` karena mengindikasikan tamu tidak membawa anak-anak. <br>
Kolom `agent` akan diisi dengan `0` karena mengindikasikan tamu melakukan reservasi tidak melalui agent. <br>
Kolom `company` akan diisi dengan `0` karena mengindikasikan tamu tidak berasal dari company. <br>
Kolom `city` akan diisi dengan `Unknown` karena kota tidak diketahui secara pasti. <br>

### 2. Mengganti tipe data dan value yang tidak sesuai
- Tipe data :
  - Feature `children` yang awalnya `float` menjadi `integer`.
  - Feature `is_canceled` dan `is_repeated_guest` yang awalnya `integer` menjadi `object`
  - Feature `agent` yang awalnya `float` menjadi `object`
- Value yang tidak sesuai <br>
  Pada Feature `meal` : mengganti value `Undefined` menjadi `No Meal` karena memiliki arti yang sama.

### 3. Membuang data yang tidak diperlukan
- Ditemukan terdapat 180 pemesanan dengan jumlah tamu = 0. Karena jumlah tamu tidak mungkin = 0, maka baris tersebut di drop.
- Ditemukan terdapat 223 pemesanan dengan jumlah tamu dewasa = 0, sedangkan children dan babies > 0. Karena kondisi ini tidak mungkin, maka baris tersebut akan di drop.
- Ditemukan terdapat 645 pemesanan dengan durasi menginap = 0, oleh karena itu baris tersebut akan di drop.
- Ditemukan terdapat 1 baris yang memiliki nilai adr < 0, sehingga baris tersebut akan di drop.

## Analysis
### 1. Monthly Booking Hotel Analysis Based on Hotel Type
Bisnis perhotelan sangat erat kaitannya dengan pelanggan. Semakin banyak pelanggan, maka semakin banyak pula revenue yang didapat. Analisa perliaku pelanggan dalam memesan hotel sangatlah penting, seperti tipe hotel apa yang paling banyak diminati dan mengaitkannya dengan kondisi musim ketika hotel dipesan.

<p align="center">
   <img src="picture/Booking Hotel during Holiday Season.png" width = 800 px alt="grafik2">
</p>

Secara keseluruhan, City hotel lebih banyak di pesan daripada Resort Hotel. Pemesanan hotel pada kedua tipe hotel rata-rata mengalami **kenaikan pada musim liburan**. Kenaikan tertinggi ada pada musim liburan pada bulan **Juni-Juli**. Hal ini dikarenakan pada bulan tersebut bertepatan dengan moment libur lebaran dan juga libur sekolah. <br>
Bulan yang memiliki pemesanan terbanyak untuk setiap tipe hotel tidak sama, pada City hotel ada pada bulan Juli dan Resort hotel ada pada bulan Juni. 
Pada akhir tahun, yaitu musim liburan pada bulan November-Desember, rata-rata pemesanan city hotel juga mengalami kenaikan tetapi tidak sebesar bulan Juni-Juli. Sedangkan untuk Resort hotel pada bulan November sempat mengalami penurunan. <br>
Setelah musim liburan, rata-rata jumlah pemesanan hotel menurun.

### 2. Impact Analysis of Stay Duration on Hotel Bookings Cancellation Rates
Selain menganalisis perilaku pelanggan dalam memesan hotel, untuk mengukur keberhasilan suatu bisnis perhotelan dapat kita lihat dari tingkat pembatalan pemesanan. Jika banyak pelanggan yang membatalkan pemesanan-nya, maka hal tersebut akan berpengaruh buruk terhadap performa bisnis hotel. Oleh karena itu analisa pengaruh durasi menginap terhadap tingkat pemesanan hotel dilakukan.

<p align="center">
   <img src="picture/Durasi menginap.png" width = 800 px alt="grafik3">
</p>

Kedua tipe hotel memiliki trend positif, dimana **semakin lama durasi menginap maka semakin tinggi kemungkinan pemesanan tersebut dibatalkan**. Selain itu dapat dilihat pula bahwa City hotel memiliki persentase pembatalan lebih besar daripada Resort hotel, dimana pada City hotel persentase pembatalan hampir 100%, sedangkan Resort hotel memiliki persentase pembatalan kurang dari 50%.

### 3. Impact Analysis of Lead Time on Bookings Hotel Cancellation Rate
Bisnis hotel biasanya memperbolehkan pelanggan memesan hotel sebelum hari kedatangannya. Jarak waktu yang terjadi pun bervariasi, ada yang hanya beberapa hari, dan ada pula pelanggan yang memesan hotel sampai beberapa bulan sebelum hari kedatangan. Sehingga dilakukan analisis untuk melihat korelasi antara lead time (jarak waktu pemesanan hotel hingga waktu kedatangan) terhadap tingkat pembatalan pemesanan hotel.

<p align="center">
   <img src="picture/Lead time.png" width = 800 px alt="grafik4">
</p>

Persentase cancel paling rendah untuk kedua tipe hotel adalah dengan lead time 1 bulan sebelum kedatangan. Resort hotel memiliki persentase cancel yang cukup stabil di kisaran 40%, sedangkan City hotel memiliki persentase pembatalan yang cukup tinggi yaitu lebih dari 60% bahkan sampe 80% ketika lead time lebih dari 8 bulan atau sekitar 1 tahun sebelum waktu kedatangan.

## Summary
1. Secara keseluruhan, City hotel paling banyak dipesan daripada Resort hotel. Pemesanan hotel, baik Resort maupun City hotel, mengalami kenaikan ketika musim liburan yaitu pada bulan **Mei-Juli** dan **Oktober-Desember**.
2. Semakin lama durasi menginap, maka 


