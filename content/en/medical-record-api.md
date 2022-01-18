---
title: Medical Records 
description: 'Dokumentasi medical record API'
position: 2 
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

## Medical Record
Untuk Menyimpan,Merubah,Mengambil data medical record.

### GET Medical Record
<code-group>
  <code-block label="Http" active>

  ```http request
  https://devdevice.cexup.com/api/medical-records/{{user_code}}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  /api/medical-record/{member_id}:
    get:
      summary: "GET api/medical-record/{member_id}"
      operationId: "getById"
      parameters:
        - name: "id"
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

#### Query Params


| Name | description        |
|------|--------------------|
| size | data count to show |
| page | pagination         |

### GET Personal

<code-group>
  <code-block label="Http" active>

  ```http request
  https://devdevice.cexup.com/api/medical-records/{{user_code}}/personal
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  /api/medical-records/{id_member}/personal:
    get:
      summary: "GET api/medical-records/{member_id}/personal"
      operationId: "getAllPersonalMedicalRecord"
      parameters:
        - name: "id_member"
          in: "path"
          required: true
          schema:
            type: "string"
      responses:
        "200":
          description: "OK"
  ```

  </code-block>
</code-group>

#### Request Header

| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|

#### Query Params


| Name | description        |
|------|--------------------|
| size | data count to show |
| page | pagination         |
| type | medical record type(optional)[enum](/medical-record-type#medical-record)     |

### GET By Type

<code-group>
  <code-block label="Http" active>

  ```http request
  https://devdevice.cexup.com/api/medical-records/{{user_code}}/personal/filter
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  /api/medical-records/{id_member}/personal:
    get:
      summary: "GET api/medical-records/{member_id}/personal/filter"
      operationId: "getAllPersonalMedicalRecord"
      parameters:
        - name: "id_member"
          in: "path"
          required: true
          schema:
            type: "string"
      responses:
        "200":
          description: "OK"
  ```

  </code-block>
</code-group>

#### Request Header

| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|

#### Query Params


| Name | description        |
|------|--------------------|
| size | data count to show |
| page | pagination         |
| type | medical record type(optional)[enum](/medical-record-type#medical-record)    |

### GET Latest
 <code-group>
  <code-block label="Http" active>

  ```http request
  https://devdevice.cexup.com/api/medical-record/{{user_code}}/latest
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  /api/medical-record/{member_id}/latest:
    get:
      summary: "GET api/medical-record/{member_id}/latest"
      operationId: "getLatestMedicalrecordByUser"
      parameters:
        - name: "id"
          in: "path"
          required: true
          schema:
            type: "string"
      responses:
        "200":
          description: "OK"
  ```

  </code-block>
</code-group>

#### Request Header

| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|

#### Query Params


| Name | description        |
|------|--------------------|
| size | data count to show |
| page | pagination         |

### GET By Id
 <code-group>
  <code-block label="Http" active>

  ```http request
  https://devdevice.cexup.com/api/medical-record/{{id_medical-record}}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
   /api/medical-record/{id}:
     get:
       summary: "GET api/medical-record/{id}"
       operationId: "getById"
       parameters:
         - name: "id"
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

### POST Medical Records

Registering device so the device can send data into medical record

<code-group>
  <code-block label="Http" active>

  ```http request
  https://devdevice.cexup.com/api/medical-record
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 /api/medical-record:
   post:
     summary: "POST api/medical-record"
     operationId: "createMeasurements"
     parameters:
       - name: "x-api-key"
         in: "header"
         required: true
         schema:
           type: "string"
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
[
  {
    "device_id":"11:FF",
    "member_id":"dsdfs",
    "nurse_id":"sada",
    "type":"BLOOD_PRESSURE",
    "value":"12",
    "method":"AUTOMATIC",
    "created_at":0,
    "assets":"ini asset",
    "diagnosis":"diagnosis",
    "note":"ini adalah note",
    "title":"bpm",
    "mime_type":"text"
  }
]
```
#### Body References
| type   | description                                                        |
|--------|--------------------------------------------------------------------|
| type   | medical record type[type](/medical-record-type#medical-record)     |
| method | medical record method[method](/medical-record-type#medical-record) |
| value  | value with type [`JSON`](medical-record-model#skema)               |

### PUT Medical Record

Registering device so the device can send data into medical record

<code-group>
  <code-block label="Http" active>

  ```http request
  https://devdevice.cexup.com/api/medical-record/{{id}}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
 /api/medical-record:
   post:
     summary: "POST api/medical-record/{id}"
     operationId: "updateMedicalRecord"
     parameters:
       - name: "x-api-key"
         in: "header"
         required: true
         schema:
           type: "string"
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
[
  {
    "device_id":"11:FF",
    "member_id":"dsdfs",
    "nurse_id":"sada",
    "type":"BLOOD_PRESSURE",
    "value":"12",
    "method":"AUTOMATIC",
    "created_at":0,
    "assets":"ini asset",
    "diagnosis":"diagnosis",
    "note":"ini adalah note",
    "title":"bpm",
    "mime_type":"text"
  }
]
```
#### Body References
| type       | description                                                        |
|------------|--------------------------------------------------------------------|
| type       | medical record type[type](/medical-record-type#medical-record)     |
| method     | medical record method[method](/medical-record-type#medical-record) |
| value      | value with type [`JSON`](medical-record-model#skema)               |

### POST Personal

Registering device so the device can send data into medical record

<code-group>
  <code-block label="Http" active>

  ```http request
  https://devdevice.cexup.com/api/medical-record/personal
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
| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|

#### Body(Form Date)

| name      | type                                          | description |
|-----------|-----------------------------------------------|-------------|
| file      | File                                          |             |
| user_id   | String                                        |             |
| type      | [type](/medical-record-type#medical-record)   |             |
| method    | [method](/medical-record-type#medical-record) |             |
| note      | String                                        |             |
| diagnosis | String                                        |             |
| title     | String                                        |             |

### PUT Personal Medical Record

Registering device so the device can send data into medical record

<code-group>
  <code-block label="Http" active>

  ```http request
  https://devdevice.cexup.com/api/medical-record/personal/{{id}}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
   /api/medical-record/personal/{id}:
    put:
      summary: "PUT api/medical-record/personal/{id}"
      operationId: "updatePersonalMedicalRecord"
      parameters:
      - name: "id"
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

#### Body(Form Date)

| name      | type                                          | description |
|-----------|-----------------------------------------------|-------------|
| file      | File                                          |             |
| user_id   | String                                        |             |
| type      | [type](/medical-record-type#medical-record)   |             |
| method    | [method](/medical-record-type#medical-record) |             |
| note      | String                                        |             |
| diagnosis | String                                        |             |
| title     | String                                        |             |

### DELETE Medical Record

Registering device so the device can send data into medical record

<code-group>
  <code-block label="Http" active>

  ```http request
  https://devdevice.cexup.com/api/medical-record/{{id}}
  ```
  </code-block>
  <code-block label="Open API">

  ```yaml
  /api/medical-record/{id}:
    delete:
      summary: "DELETE api/medical-record/{id}"
      operationId: "deleteMedicalRecord"
      parameters:
      - name: "id"
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
