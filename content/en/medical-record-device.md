---
title: Device
description: 'Dokumentasi medical record Device API'
position: 3
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

## Device
Feature device IoT management:

### GET  list devices

Getting devices that has registered into database Cexup

<code-group>
  <code-block label="Http" active>

  ```http request
   https://devdevice.cexup.com/api/devices
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 /api/devices:
   get:
     summary: "GET api/devices"
     operationId: "getAll"
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

### GET  detail device

Getting devices that has registered into database Cexup

<code-group>
  <code-block label="Http" active>

  ```http request
   https://devdevice.cexup.com/api/device/{id_device}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  /api/device/{id_device}:
    get:
      summary: "GET api/device/{id_device}"
      operationId: "get"
      parameters:
        - name: "id_device"
          in: "path"
          required: true
          schema:
            type: "number"
            format: "int64"
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

### POST  new device

Registering device so the device can send data into medical record

<code-group>
  <code-block label="Http" active>

  ```http request
   https://devdevice.cexup.com/api/devices
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  /api/device/{id_device}:
    get:
      summary: "GET api/device/{id_device}"
      operationId: "get"
      parameters:
        - name: "id_device"
          in: "path"
          required: true
          schema:
            type: "number"
            format: "int64"
      responses:
        "200":
          description: "OK"
  ```

  </code-block>
</code-group>

#### Request Header



| x-api-key | text(required) |
|-----------|----------------|

#### Body
```json
[
    
    {
        "device_name": "E86 5894",
        "device_mac": "D0:61:AE:D4:58:94",
        "device_type": "CONSUMER",
        "device_holder": "unknown"
    }
]
```

#### Body References
| type | description |
|-----------|------------------------------------------------|
|device_type| [type](/medical-record-type#device)|



### PUT  existing device

Registering device so the device can send data into medical record

<code-group>
  <code-block label="Http" active>

  ```http request
   https://devdevice.cexup.com/api/device
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  /api/device/{id_device}:
    put:
      summary: "PUT api/device/{id_device}"
      operationId: "update"
      parameters:
        - name: "id_device"
          in: "path"
          required: true
          schema:
            type: "number"
            format: "int64"
      responses:
        "200":
          description: "OK"
  ```

  </code-block>
</code-group>

#### Request Header

| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|

#### Body
```json
{
  "device_name": "string,uniq",
  "device_mac": "string,uniq",
  "device_type": "string(CONSUMER/CORPORATE)",
  "device_holder": "string(hospital)"
}
```
#### Body References
| type | description |
|-----------|------------------------------------------------|
|device_type| [type](/medical-record-type#device)|