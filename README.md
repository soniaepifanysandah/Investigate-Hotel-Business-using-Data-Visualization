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


