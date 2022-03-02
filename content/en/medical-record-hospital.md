---
title: Hospital
description: 'Dokumentasi medical record API'
position: 4 
category: Medical Record
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
Dokumentasi berikut bertujuan untuk memandu anda dalam menggunakan data medical record pada aplikasi Cexup. Jika Anda bekerja untuk/di Cexup anda dapat menghubungi projek manajer untuk lebih detail.

## Introduce

Sebelum memulai perlu dicatat bahwa `API` berikut digunakan untuk semua aplikasi dibawah naungan Cexup atau kita sebut `White Label` menggunakan `API` yang sama untuk medical recordnya, termasuk web,mobile,desktop dan lain sabagainya. `API` menggunakan protokol `Http REST` untuk komunikasi antara server dan client. Setiap request mewajibkan menambahkan header `x-api-key` jika belum memiliki `api-key` silahkan hubungi developer Cexup.


## Hospital
Hospital Management

### GET list hospital
Get list available hospital 

<code-group>
  <code-block label="Http" active>

  ```http request
   https://devdevice.cexup.com/api/hospitals
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  /api/hospitals:
    get:
      summary: "GET api/hospitals"
      operationId: "getAllHospitals"
      responses:
        "200":
          description: "OK"
  ```

  </code-block>
</code-group>

#### Request Header

| x-api-key | text(required) |
|-----------|----------------|

#### Query Params


| Name | description        |
|------|--------------------|
| size | data count to show |
| page | pagination         |




### GET detail hospital

<code-group>
  <code-block label="Http" active>

  ```http request
   https://devdevice.cexup.com/api/hospital/{{hospital_id}}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  /api/hospitals:
    get:
      summary: "GET api/hospital/{hospital_id}"
      operationId: "getAllHospitals"
      responses:
        "200":
          description: "OK"
  ```

  </code-block>
</code-group>

#### Request Header

| x-api-key | text(required) |
|-----------|----------------|

#### Query Params


| Name | description        |
|------|--------------------|
| size | data count to show |
| page | pagination         |
