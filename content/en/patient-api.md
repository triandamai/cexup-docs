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
These docs covered about basic implementation Authentication API Cexup. if you work for/at Cexup you can use these docs
or contact your Project Manager for more detail.

## Introduce

Before you begin please note this API can be use for all white labeled Cexup application including web,mobile,and other.
The API use `REST` for communication between client and server. There are important element you must include in every
request on this API, header with `x-api-key` contact developer for getting api key.

## Authentication
Authentication management

### POST Login
<code-group>
  <code-block label="Http" active>

  ```http request
    https://app.cexup.com/api/login/patient
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

#### Body


| Name     | description                        |
|----------|------------------------------------|
| email    | required (username/email) (string) |
| password | required  (string)                 |

### POST Register Patient

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/register/patient
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


| Name     | description        |
|----------|--------------------|
| name     | required (string)  |
| address  | required (string)  |
| username | required (unique:users)  regex:/(^([a-zA-Z]+)(\d+)?$)/u'  (string)     |
| email    | required (email unique:users) (string)  |
| password | required (string)  |

### POST Register Check Id

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/register/check-id/{type}
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


#### Query Params


| Name      | description                     |
|-----------|---------------------------------|
| username  | ((string) {username: optional}) |
| email     | ((string) {username: optional}) |

### POST Update User
 <code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/update/{role}
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

#### Body


| Name         | description                          |
|--------------|--------------------------------------|
| user_id      | (text)                               |
| name         | (string) {name: optional}            |
| address      | (text) {address: optional}           |
| gender       | (string) {gendeer: optional}         |
| phone_number | (string) {phone_number: optional}    |
| type         | (enum : ktp, nik, passport, kitas) opsinal         |
| no_type      | (string) optional                    |

### POST Change Avatar
 <code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/avatar
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

#### Body

| Name         | description                             |
|--------------|-----------------------------------------|
| user_id      | required (text)                         |
| file         | required (file) base64                  |
| type         | required (string) { type: png|jpeg|.. } |

## Menu Patient
Feature Menu Patient management:

### POST List Doctor

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/doctor
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


| Name | description        |
|------|--------------------|
| data | data count to show |
| page | pagination         |

### GET  List Speciality

Getting devices that has registered into database Cexup

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/speciality
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


| Name | description        |
|------|--------------------|
| data | data count to show |
| page | pagination         |

### POST  Detail Doctor

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/doctor/show
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

| Name | description        |
|------|--------------------|
| slug | required (string)  |



### POST List Artikel



<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/article
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
| Name | description        |
|------|--------------------|
| data | data count to show |
| page | pagination         |


### POST Detail Artikel

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/article/show
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

| Name | description        |
|------|--------------------|
| slug | required (string)  |

### POST list hospital
Get list available hospital 

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/hospital
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
| Name | description        |
|------|--------------------|
| data | data count to show |
| page | pagination         |


### POST detail hospital

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/hospital/show
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

| Name | description        |
|------|--------------------|
| slug | required (string)  |

### POST Get Time

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/doctor/get-time-list
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

| Name                   | description            |
|------------------------|------------------------|
| doctor_has_hospital_id | required (int)         |
| date                   | date_format ( Y-m-d )  |
| appointment            | (string)               |

### POST Booking Doctor

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/doctor/booking
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

| Name                   | description                       |
|------------------------|-----------------------------------|
| username               | required (string)                 |
| username_doctor        | required (string)                 |
| user_id                | required (text)                   |
| id                     | required (int)                    |
| time                   | required (string)                 |
| type                   | required (enum = reservasi / call)|
| patient                | required (string)                 |
| price                  | required (string)                 |

### POST List Order

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/user/orders
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

| Name                   | description            |
|------------------------|------------------------|
| user_id                | (text)                 |
| data                   | (int)                  |
| appointment            | (string)               |
| type                   | (enum = pending / booked / apointment / finish / failed)  |

### POST Detail Order

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/user/order/show
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

| Name                   | description            |
|------------------------|------------------------|
| transaction_id         | required (string)      |

### PUT Reschedulle Order

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/user/orders
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

| Name                   | description            |
|------------------------|------------------------|
| transaction_id         | required (string)      |
| type                   | required (enum = accept / reject_by_patient / reschedulle_patient) |


### PUT Cancel Order

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/user/orders
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

| Name                   | description            |
|------------------------|------------------------|
| transaction_id         | required (string)      |
| type                   | required (enum = accept / reject_by_patient / reschedulle_patient) |

### GET List Produk

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/ecommerce/product?page=1
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  
  ```

  </code-block>
</code-group>


#### Body
| Name | description        |
|------|--------------------|
| data | data count to show |
| page | pagination         |

### GET List Katagori product

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/ecommerce/category?page=1?data=10
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

 Name | description         |
|------|--------------------|
| data | data count to show |
| page | pagination         |

### GET Detail Product

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/ecommerce/product/slug-product
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

 Name | description         |
|------|--------------------|
| slug | required (string)  |


### GET List Product Katagori

<code-group>
  <code-block label="Http" active>

  ```http request
   https://app.cexup.com/api/ecommerce/category/slug-category
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

 Name | description         |
|------|--------------------|
| slug | required (string)  |

### POST Obgyn Profile

Registering device so the device can send data into medical record

<code-group>
  <code-block label="Http" active>

  ```http request
https://app.cexup.com/api/obgyn
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
    "user_id": "eyJpdiI6Ik1ZdjVad2Rrd2VUc2psa0NueGFWMXc9PSIsInZhbHVlIjoibDVMYUliRk1MejArVkNWNG1yakszUT09IiwibWFjIjoiOTM2ZTE0Njc0MDkyZDgzYmRjODUzODM5Njc5NmIxN2M3MjMxZTNmMzZlMDYxNTFjZmNlNzY5MzA4YmMzMWY4ZCJ9",
    "suami": "papa - required",
    "faskes1": "faskes1 - optional",
    "faskes_rujukan": "rujukan - optional",
    "pendidikan": "sd/smp/sma/diploma/sarjana/etc... - optional",
    "pekerjaan": "Direktur/etc... - optional"
}
```

