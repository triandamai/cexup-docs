---
title: API 
description: 'documentation for Patient API'
position: 14 
category: Doctor
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
Dokumentasi berikut bertujuan untuk memandu anda dalam menggunakan data Dokter pada aplikasi Cexup. Jika Anda bekerja untuk/di Cexup anda dapat menghubungi projek manajer untuk lebih detail.

## Introduce

Sebelum memulai perlu dicatat bahwa `API` berikut digunakan untuk semua aplikasi dibawah naungan Cexup atau kita sebut `White Label` menggunakan `API` yang sama untuk COrporate, termasuk web,mobile,desktop dan lain sabagainya. `API` menggunakan protokol `Http REST` untuk komunikasi antara server dan client. beberapa request mewajibkan menambahkan header `Authorization` jika belum memiliki `Bearer Token` silahkan hubungi developer Cexup.

## Authentication
Authentication management

### POST Login Doctor
<code-group>
  <code-block label="Http" active>

  ```http request
    https://pusdokkes-app.cexup.com/api/login/doctor
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
| x-api-key     | x-api-key        |

#### Body

```json
{
    "username": "isman08",
    "password": "password"
}
```

#### Tests

```json
{success,message,user} `{ success: true, message: Success, user: User Resource}`
```


### POST User Update

<code-group>
  <code-block label="Http" active>

  ```http request
   https://pusdokkes-app.cexup.com/api/update/doctor
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
   https://pusdokkes-app.cexup.com/api/avatar
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
## Menu Doctor
Feature Menu Doctor management:

### POST Doctor Order Summary

<code-group>
  <code-block label="Http" active>

  ```http request
   https://pusdokkes-app.cexup.com/api/doctor/summary/1
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


### GET  Doctor List

<code-group>
  <code-block label="Http" active>

  ```http request
   https://pusdokkes-app.cexup.com/api/doctor/orders/1?appointment=call&type=missed&page=1&data=10
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

#### Query Params

| Key           | Value            | 
|---------------|------------------|
| appointment   | call             |  
| type          | missed           |
| page          | 1                |
| data          | 10               |


### GET User Order Show

<code-group>
  <code-block label="Http" active>

  ```http request
   https://pusdokkes-app.cexup.com/api/orders/show/PSDS-MT6209fa6b1ad85
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

## Menu EWS
Feature Menu EWS untuk Aplikasi Doctor :

### GET Ews List Summary for Doctor
 

<code-group>
  <code-block label="Http" active>

  ```http request
   https://pusdokkes-app.cexup.com/api/ews/patient/{doctor_id}
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


### GET EWS List Patient for Doctor

<code-group>
  <code-block label="Http" active>

  ```http request
    https://pusdokkes-app.cexup.com/api/ews/patient/{doctor_id}/{status}
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


### GET EWS Patient History

<code-group>
  <code-block label="Http" active>

  ```http request
   https://pusdokkes-app.cexup.com/api/ews/history/{user_code}?page=1&data=10
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


#### Query Params

| Key           | Value            | 
|---------------|------------------|
| page          | 1                |
| data          | 10               |

### POST Doctor Note

<code-group>
  <code-block label="Http" active>

  ```http request
   https://pusdokkes-app.cexup.com/api/user/order/doctor-note
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
  "transaction_id": "PSDS-MT621f63278829c",
  "subjective": "<p>Subjective</p>",
  "objective": "<p>Objective</p>",
  "assesment": [
  	{
  		"id": "741241668",
  		"name": "Screening for Covid"
  	}
  ],
  "planing": {
    "non_medical_mentosa": "<p>Non medical mentosa</p>",
    "procedure": "<p>Procedure/saran</p>",
    "medical_mentosa": [
      {
        "name": "nama_obat",
        "qty": 6,
        "per_day": "3x",
        "instruction": "sesudah makan"
      },
      {
        "name": "nama_obat",
        "qty": 6,
        "per_day": "3x",
        "instruction": "sesudah makan"
      }
    ]
  }
}
  
  ```