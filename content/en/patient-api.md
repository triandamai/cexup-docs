---
title: API 
description: 'documentation for Patient API'
position: 12 
category: Patient
---
<style>
td, th {
   border: none!important;
}
.prose thead{
    border-bottom-width: 0px !important;
}
</style>
<alert type="success">

New documentation cexup

</alert>
Dokumentasi berikut bertujuan untuk memandu anda dalam menggunakan data Pasien pada aplikasi Cexup. Jika Anda bekerja untuk/di Cexup anda dapat menghubungi projek manajer untuk lebih detail.

## Introduce

Sebelum memulai perlu dicatat bahwa `API` berikut digunakan untuk semua aplikasi dibawah naungan Cexup atau kita sebut `White Label` menggunakan `API` yang sama untuk COrporate, termasuk web,mobile,desktop dan lain sabagainya. `API` menggunakan protokol `Http REST` untuk komunikasi antara server dan client. beberapa request mewajibkan menambahkan header `Authorization` atau `x-api-key` jika belum memiliki `Bearer Token` dan `{x-api-key}`  silahkan hubungi developer Cexup.

## Authentication
Authentication management

### POST Login
<code-group>
  <code-block label="Http" active>

  ```http request
    {base_url}/login/patient
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | {x-api-key}      |

#### Body

```json
{
    "email": "fahmi@gmail.com",
    "password": "12345678"
}
```

#### Tests

```json
{success,message,user} `{ success: true, message: Success, user: User Resource}`
```

### POST Login Providers
<code-group>
  <code-block label="Http" active>

  ```http request
    {base_url}/login/provider/{name}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |


#### Body

```json
{
    "email":"zidni.mujib5@gmail.com"
}
```


### POST Register Patient

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/register/patient
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 
  ```

  </code-block>
</code-group>



#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | {x-api-key}      |

#### Body

```json
{
    "name" : "Afri Ismanto Hidayat",
    "username" : "isman081",
    "email" : "afrihidayat@gmail.com",
    "password" : "password",
    "address" : "Address here"
}
```


### POST User Update

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/update/patient
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Token Bearer     |


#### Body

 ```json
 {
    "user_id": "eyJpdiI6Im5JMVBlTWZaVytmNVJmaVphQzE4K1E9PSIsInZhbHVlIjoiUmhSSlBsNmM5SjhMblpXOGpYc3BXUT09IiwibWFjIjoiZGI1MWE0ZDdjNGNhMzBlNGU4N2RlOGJhNDFjMmJmYmE5OTMzYzAzY2RkYjcyMDdjNzFjYTNlMGZlYzg5YTZkZiJ9",
    "name": "John Doe",
    "address": "adress here",
    "gender": "perempuan / laki-laki",
    "date_of_birth": "Y-m-d (2020-01-22)",
    "phone_number": "085xxx",
    "provinsi_id": "1",
    "kabupaten_id": "1",
    "kecamatan_id": "1",
    "desa_id": "2"
}
  ```


### POST User Avatar
 <code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/avatar
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
   
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| Authorization | Bearer Token     |
| accept        | application/json |

#### Body

  ```json
   {
    "user_id": "adsd",
    "file": "base64_encode",
    "extension": "jpg/png"
}
  ```
## Menu Patient
Feature Menu Patient management:

### GET List Doctor

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/api/doctor
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |



### GET  Detail Doctor

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/api/doctor/{slug}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |


### POST Doctor Get Time List

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/doctor/get-time-list
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| x-api-key     | {{x-api-key}}    |

#### Body


  ```json
  {
    "doctor_has_hospital_id" : "73",
    "date" : "2022-01-14",
    "appointment" : "call/reservation"
  }
  ```
### GET List hospital
Get list available hospital 

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/hospitals
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |



### GET Detail hospital

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/hospitals/klinik-satelit-ui-makaras
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |

### GET Hospital List Doctor

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/hospitals/klinik-satelit-ui-makara/doctors
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |


### GET  List Speciality



<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/speciality
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |



### GET  Speciality Doctor List

Getting devices that has registered into database Cexup

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/doctor/speciality/{slug}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |

#### Body

 ```json
  {
    "slug":"umum"
  }
  ```

  
## Wilayah
### GET Wilayah
<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}wilayah
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| x-api-key     | x-api-key        |

### GET Detail Wilayah
<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}wilayah/64
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| x-api-key     | x-api-key        |


## E-Commerce
### GET Category E-commerce

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/ecommerce/category
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |


### GET Category E-commerce Show List Product

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/ecommerce/category/smartwatch
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |

### GET Product E-commerce List

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/ecommerce/product
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |

### GET Product E-commerce Show

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/ecommerce/product/cexme-e86-health-smartwatch---hitam
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |

#### Body (Response)
```json
  {
    "code": "200",
    "success": true,
    "message": "Ok",
    "data": {
        "id": 16,
        "category": 11,
        "slug": "cexme-e86-health-smartwatch---hitam",
        "title": "CeXme E86 Health Smartwatch - Hitam",
        "description": "<ul><li><span style=\"color: var(--N700,rgba(49,53,59,0.68));\">Kondisi:&nbsp;</span><span style=\"color: var(--N700,rgba(49,53,59,0.96));\">Baru</span></li><li><span style=\"color: var(--N700,rgba(49,53,59,0.68));\">Berat:&nbsp;</span><span style=\"color: var(--N700,rgba(49,53,59,0.96));\">200 Gram</span></li><li><span style=\"color: var(--N700,rgba(49,53,59,0.68));\">Kategori:&nbsp;</span><a href=\"https://www.tokopedia.com/p/handphone-tablet/wearable-devices/smart-watch\" rel=\"noopener noreferrer\" target=\"_blank\" style=\"color: var(--G500,#03AC0E);\"><strong>Smart Watch</strong></a></li><li><span style=\"color: var(--N700,rgba(49,53,59,0.68));\">Etalase:&nbsp;</span><a href=\"https://www.tokopedia.com/telecexup/etalase/all\" rel=\"noopener noreferrer\" target=\"_blank\" style=\"color: var(--G500,#03AC0E);\"><strong>Semua Etalase</strong></a></li></ul><p><strong style=\"color: var(--G500,#03AC0E);\"><span class=\"ql-cursor\">﻿﻿﻿﻿﻿﻿﻿﻿﻿﻿﻿﻿</span></strong></p><p>CeXme E86 Health Smartwatch</p><p><br></p><p>Health Smartwatch ini didesain khusus untuk memantau status kesehatanmu seperti :</p><p>- Body Temperature</p><p>- Blood Oxygen (Saturasi Oksigen - SPO2)</p><p>- Blood Pressure.</p><p>- Respiratory Rate</p><p>- Heart Rate</p><p>- ECG yg dilengkapi dengan analisa dari Artificial Intelligence.</p><p><br></p><p>CeXme Health Smartwatch ini sudah ditest akurasinya oleh beberapa Rumah Sakit di Indonesa, dengan ketepatan lebih dari 95% dibanding dengan peralatan kesehatan manual.</p><p><br></p><p>CeXme Health Smartwatch menyediakan aplikasi untuk individual: Smarthealth yg bisa didownload di Playstore &amp; App Store, dan dalam waktu dekat ini akan terkoneksi ke applikasi Rumah Sakit, sehingga anda dapat mengkonsultasikan status kesehatan anda melalui aplikasi Telemedicine Rumah Sakit.</p><p><br></p><p>CeXme baik digunakan untuk setiap orang untuk memantau kesehatan pribadi atau kesehatan orang tua ato pasien yg memiliki masalah kesehatan secara umum hingga penyakit jantung, karena dapat secara otomatis memantau Vital Sign setiap jamnya, sehingga dokter bisa mendapatkan data kesehatan anda secara akurat.</p><p><br></p><p><br></p><p>Catatan :</p><p>1. Walaupun Smartwatch ini untuk kesehatan, namun Smartwatch ini juga dapat digunakan untuk keperluan olah raga, entertainment, reminder, dll.</p><p>2. Apabila pemakai Smartwach ini menderita Kormobid, silahkan lakukan Kalibrasi Blood Pressurenya melalui aplikasi Rumah Sakit, karena standar Blood Pressure ini menggunakan standar orang sehat.</p><p>3. Segera hubungi Dokter ato Rumah Sakit, apabila menemukan ketidak normalan.</p><p>4. Jumlah Smartwatch ini sangat terbatas, apabila stock habis, silahkan melakukan PreOrder, baranng akan dikirimkan sekitar 2-4 minggu dari tanggal pemesanan.</p><p>5. Untuk keperluan Charging, mohon menggunakan Charger biasa yg ukurannya dibawah 2 ampere. Apabila tidak ada, silahkan charge melalui laptop ato komputer. Jangan menggunakan fast charger, karena Garansinya akan gugur.</p><p>6. Masa garansi : 12 (Dua belas) bulan</p>",
        "price": "2250000.00",
        "stock": 100,
        "view": 60,
        "link": "https://www.tokopedia.com/telecexup/cexme-e86-health-smartwatch-hitam?whid=0",
        "thumb": "http://localhost:8082/storage/products//136/conversions/eqgoXtnLTCSUtbUY-original.jpg",
        "original": [
            "http://localhost:8082/storage/products//136/conversions/eqgoXtnLTCSUtbUY-original.jpg",
            "http://localhost:8082/storage/products//137/conversions/IIBX0fIQRtiV5Q6S-original.jpg",
            "http://localhost:8082/storage/products//196/conversions/kVu6cGGP9bLsqETf-original.jpg"
        ]
    }
}
  ```
### GET Wishlist List

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/ecommerce/wishlist/{user_id}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |

#### Body (Response)
```json
  {
    "code": "200",
    "success": true,
    "message": "Ok",
    "data": []
}
  ```
### POST Wishlist Store

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/ecommerce/wishlist
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |

#### Body
```json
 {
    "user_id": "eyJpdiI6InMzWW10S1kxazNoSGhuUFFzaUJJQ2c9PSIsInZhbHVlIjoiNml0VmpcLzJFd0VTSHBTWk91aHRvTlE9PSIsIm1hYyI6IjdhZmU0MWYzNGQ5YTZkOTEyNzZhMTBkZTUzOWI5NTNlMjZlZmZmYzNmYzlhNmU4YjYyOWI0ZmZhNjNiYjhkZTYifQ==",
    "product_id": "16"
}
  ```
### DEL Wishlist Remove

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/ecommerce/wishlist/{wishlist_id}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |



## Artikel
### GET List Artikel



<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/article
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |

### GET Detail Artikel

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/article/6-cara-menjaga-kesehatan-tubuh
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| x-api-key     | x-api-key        |



## Order 

### POST Appointment Booking

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/doctor/booking
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Bearer Token     |

#### Body

```json
{
    // "username" : "required",
    "username_doctor" : "required",
    "user_id" : "required",
    "id" : "time_id ( appointment_setting_id )",
    "time" : "12:00-13:00",
    "type" : "call / reservation",
    "patient" : "name patient",
    // "price" : "required",
    "allow_access_data" : true
}
```


### PUT Cancel Order By Patient

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/user/orders
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Bearer Token     |

#### Body

```json
  
{
    "transaction_id": "PSDS-MT61ff9e960134c",
    "type": "reject_by_patient",
    "bank_name": "BCA",
    "account_number": "333",
    "account_name": "Account Name"
}
  ```

### PUT Cancel Order By Doctor

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/user/orders
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Bearer Token     |

#### Body

```json
{
    "transaction_id": "PSDS-MT61ff9e960134c",
    "type": "reject"
}
  ```

### PUT Order Reschedule

<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}user/orders
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Bearer Token     |

#### Body

```json
  
{
    "transaction_id": "PSDS-MT623d7a1270804",
    "type": "reschedule",
    "date": "2022-03-25",
    "time": "17:00"
}
  ```

### PUT Order Accept

<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}user/orders
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Bearer Token     |

#### Body

```json
  
{
    "transaction_id": "cxp-xxxxx",
    "type": "accept"
}
  ```


## Obgyn
### POST Obgyn Store

Registering device so the device can send data into medical record

<code-group>
  <code-block label="Http" active>

  ```http request
{base_url}/obgyn
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 
  ```

  </code-block>
</code-group>

#### Request Header
| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Bearer Token     |

#### Body
```json
{
    "user_id": "eyJpdiI6Ik1ZdjVad2Rrd2VUc2psa0NueGFWMXc9PSIsInZhbHVlIjoibDVMYUliRk1MejArVkNWNG1yakszUT09IiwibWFjIjoiOTM2ZTE0Njc0MDkyZDgzYmRjODUzODM5Njc5NmIxN2M3MjMxZTNmMzZlMDYxNTFjZmNlNzY5MzA4YmMzMWY4ZCJ9",
    "suami": "papa - required",
    "faskes1": "faskes1 - optional",
    "faskes_rujukan": "rujukan - optional",
    "pendidikan": "sd/smp/sma/diploma/sarjana/etc... - optional",
    "pekerjaan": "Direktur/etc... - optional"
}
```

### GET Obgyn

Registering device so the device can send data into medical record

<code-group>
  <code-block label="Http" active>

  ```http request
{base_url}/obgyn/{user_id}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 
  ```

  </code-block>
</code-group>

#### Request Header
| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Bearer Token     |

## EWS (Early Warning Score)
### POST EWS

<code-group>
  <code-block label="Http" active>

  ```http request
  {base_url}/ews
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 
  ```

  </code-block>
</code-group>

#### Request Header
| Key           | Value            | 
|---------------|------------------|
| x-api-key     | {{x-api-key}}    |


#### Body
```json
{
    "user_code":"AMSe5Sn8Gkxj7",
    "point": 3,
    "result":"sedang",
    "produce_at": "1632889813001"
}
```

### GET Ews Patient Current


<code-group>
  <code-block label="Http" active>

  ```http request
  {base_url}/ews/PSDSDAOtl37m5G
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 
  ```

  </code-block>
</code-group>

#### Request Header
| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Bearer Token     |


## Family Tree
### Get Family


<code-group>
  <code-block label="Http" active>

  ```http request
  {{api_url}}family
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 
  ```

  </code-block>
</code-group>

#### Request Header
| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Bearer Token     |




### POST Add personal family


<code-group>
  <code-block label="Http" active>

  ```http request
  {{api_url}}family
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 
  ```

  </code-block>
</code-group>

#### Request Header
| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Bearer Token     |

#### Body


  ```json
    {
        "child_code":"RUIkDyPXmAshD",
        "child_type":"family_member"
    }
  ```

### PATCH Accept invited


<code-group>
  <code-block label="Http" active>

  ```http request
  {{api_url}}family/accept/eyJpdiI6ImNBUlJ5MUppc2RRTmJsNmk4dUN0NXc9PSIsInZhbHVlIjoiMkZkZlJUNEtnNVZjdDAxWmxoK2NDQT09IiwibWFjIjoiZWU1NmM1NWEzNDQyMTc4ZWUxM2Q3ZWE3YzQ1MTY5YmIxZGVhNzc2ZjhiYTRkNzhkNjU5NjMzNzVlZDYyZWFkYyJ9
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 
  ```

  </code-block>
</code-group>

#### Request Header
| Key           | Value            | 
|---------------|------------------|
| Content-Type  | application/json |
| accept        | application/json |
| Authorization | Bearer Token     |

