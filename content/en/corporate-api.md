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

Sebelum memulai perlu dicatat bahwa `API` berikut digunakan untuk semua aplikasi dibawah naungan Cexup atau kita sebut `White Label` menggunakan `API` yang sama untuk COrporate, termasuk web,mobile,desktop dan lain sabagainya. `API` menggunakan protokol `Http REST` untuk komunikasi antara server dan client. beberapa request mewajibkan menambahkan header `Authorization` jika belum memiliki `Bearer Token` silahkan hubungi developer Cexup.

## Authentication
Untuk Menyimpan,Merubah,Mengambil data Corporate.

### POST Login Nurse
<code-group>
  <code-block label="Http" active>

  ```http request
    https://dev-admin.cexup.com/api/login
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


#### Body

```json
{
    "email": "dwilinasofiati@gmail.com",
    "password": "password2"
}
```


### GET User

<code-group>
  <code-block label="Http" active>

  ```http request
   https://dev-admin.cexup.com/api/user/dwilinasofiati@gmail.com
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



### PATCH Setting Password

<code-group>
  <code-block label="Http" active>

  ```http request
   https://dev-admin.cexup.com/api/settings/password
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
| Accept        | application/json |


#### Body

```json
{
    "password": "password2",
    "password_confirmation": "password2"
}
```
## Main Menu

### GET Patient List
 <code-group>
  <code-block label="Http" active>

  ```http request
   https://dev-admin.cexup.com/api/settings/password
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



### GET Patient List With Query
 <code-group>
  <code-block label="Http" active>

  ```http request
   https://dev-admin.cexup.com/api/patients?query[name]=zidnid
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

| Name         | description                             |
|--------------|-----------------------------------------|
| query[name]  |                        |



### GET Patient Show

<code-group>
  <code-block label="Http" active>

  ```http request
   https://dev-admin.cexup.com/api/patients/{user_code}  
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


### POST Patient Store

Getting devices that has registered into database Cexup

<code-group>
  <code-block label="Http" active>

  ```http request
  https://dev-admin.cexup.com/api/patients
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
    "name": "John Doe",
    "email": "example@gmail.com",
    "gender": "laki-laki/perempuan",
    "address": "Example Address",
    "username": "exampleUsername",
    "password": "password",
    "confirm_password": "password",
    "phone_number": "081xxxxxx"
}
```

### PATCH Patient Update

<code-group>
  <code-block label="Http" active>

  ```http request
   https://dev-admin.cexup.com/api/patients/{user_code}
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
    "name": "John Doe",
    "gender": "laki-laki/perempuan",
    "address": "Example Address",
    "isreset": false,
    "password": null,
    "confirm_password": null,
    "phone_number": "081xxxxxx"
}
```


### GET Check Available Username



<code-group>
  <code-block label="Http" active>

  ```http request
   https://dev-admin.cexup.com/api/user/check/username/{exampleUsername}
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




### GET Check Available Email

<code-group>
  <code-block label="Http" active>

  ```http request
   https://dev-admin.cexup.com/api/user/check/email/{example@gmail.com}
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


### GET Check Available No_Type
Get list available hospital 

<code-group>
  <code-block label="Http" active>

  ```http request
   https://dev-admin.cexup.com/api/user/check/no_type/{33021xxxx}
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
   https://dev-app.cexup.com/api/wilayah
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
   https://dev-app.cexup.com/api/wilayah/11
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
