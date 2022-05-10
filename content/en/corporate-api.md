---
title: API 
description: 'documentation for Corporate API'
position: 13 
category: Corporate
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
Dokumentasi berikut bertujuan untuk memandu anda dalam menggunakan data Corporate pada aplikasi Cexup. Jika Anda bekerja untuk/di Cexup anda dapat menghubungi projek manajer untuk lebih detail.

## Introduce

Sebelum memulai perlu dicatat bahwa `API` berikut digunakan untuk semua aplikasi dibawah naungan Cexup atau kita sebut `White Label` menggunakan `API` yang sama untuk COrporate, termasuk web,mobile,desktop dan lain sabagainya. `API` menggunakan protokol `Http REST` untuk komunikasi antara server dan client. beberapa request mewajibkan menambahkan header `Authorization` atau `x-api-key` jika belum memiliki `Bearer Token` dan `{x-api-key}`  silahkan hubungi developer Cexup.

## Authentication
Untuk Menyimpan,Merubah,Mengambil data Corporate.

### POST Login Nurse
<code-group>
  <code-block label="Http" active>

  ```http request
    {base_url}/login
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
| x-api-key     | {{x-api-key}}    |

#### Body

```json
{
    "email": "dwilinasofiati@gmail.com",
    "password": "password2"
}
```


### POST Nurse Update

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/update/nurse
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
     "password": "password2"
    
}
  ```

### POST Register Pasien

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
| x-api-key     | {{x-api-key}}    |


#### Body

```json
{
    "name" : "Afri Ismanto Hidayat",
    "username" : "isman0832",
    "email" : "afrihidayat832@gmail.com",
    "password" : "password",
    "address" : "Address here"
}
```

### POST Change Password
 <code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}change-password/{role}
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
| Accept        | application/json |
| Authorization | Bearer Token     |

#### Body

```json
{
    "password": "12345678"
}
  ```

## Main
### GET Patient With Current Disease
 <code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}nurse/patients-disease
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
| Accept        | application/json |
| Authorization | Bearer Token     |



### GET Patient Show

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}nurse/patients/{user_code}  
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
| Accept        | application/json |
| Authorization | Bearer Token     |


### GET Top 10 Disease

<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}patients-disease
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
| Accept        | application/json |
| Authorization | Bearer Token     |

## Wilayah

### GET Provinsi

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/wilayah
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


### GET Find

<code-group>
  <code-block label="Http" active>

  ```http request
   {base_url}/wilayah/11
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



## ICD11

### GET ICD11

<code-group>
  <code-block label="Http" active>

  ```http request
   https://id.who.int/icd/entity/search?q=diabet
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>

#### Request Header

| Key             | Value            | 
|-----------------|------------------|
| Content-Type    | application/json |
| accept-language | en               |
| Authorization   | Bearer Token     |
| API-Version     | v2               |

#### Query Params

| Key                    | Value                             |
|------------------------|-----------------------------------|
| q                      | diabet                            |


### POST Get Token WHO

<code-group>
  <code-block label="Http" active>

  ```http request
   https://icdaccessmanagement.who.int/connect/token
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

#### Body (Form Data)

| Name                   | Value                  |
|------------------------|------------------------|
| grant_type             | client_credentials     |
| scope                  | icdapi_access          |
| client_id              | c0d16ff1-714c-4657-bdc3-8c8027d4efef_f266bfb8-1b03-4895-9988-95b1956de98a  |
| client_secret          | 1F0fqZOaOkkVx/65vuy3Bbh6sGqoSfw5o3uKN90VjEE= |


## EWS
### GET Ews Patient Current

<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}ews/PSDSDAOtl37m5G
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
| Accept        | application/json |
| Authorization | Bearer Token     |


### GET Ews Patient History

<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}ews/history/PSDStj5DlgdJFh?page=2&data=1
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
| Accept        | application/json |
| Authorization | Bearer Token     |


#### Query Params

| Key           | Value | 
|---------------|-------|
| Page          | 2     |
| data          | 1     |


### GET Summary EWS Per-Faskes

<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}nurse/ews
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
| Accept        | application/json |
| Authorization | Bearer Token     |


## Doctor
### GET Doctor List per Faskes

<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}nurse/doctor
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
| Accept        | application/json |
| Authorization | Bearer Token     |


### GET Doctor Show

<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}doctor/{slug}
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
| Accept        | application/json |
| x-api-key     | {x-api-key}      |


### GET Qr Code Doctor

<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}nurse/qr/generate/{slug}
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
| Accept        | application/json |
| Authorization | Bearer Token     |


## Family Tree Corporate
### POST Nurse Add Family Tree

<code-group>
  <code-block label="Http" active>

  ```http request
   {{api_url}}nurse/patient/addFamilyTree
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
| Accept        | application/json |
| Authorization | Bearer Token     |

#### Body

 ```json
 {
    "parent_code": "RUIUAwLrrLeRC",
    "child_name": "Farhan Aditya",
    "child_type": "child"
}
 
  ```