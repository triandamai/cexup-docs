---
title: API 
description: 'documentation for Medical Record API'
position: 1 
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

These docs covered about basic implementation Medical Record API Cexup. if you work for/at Cexup you can use these docs
or contact your Project Manager for more detail.

## Introduce

Before you begin please note this API can be use for all white labeled Cexup application including web,mobile,and other.
The API use `REST` for communication between client and server. There are important element you must include in every
request on this API, header with `x-api-key` contact developer for getting api key.

## Medical Record
Medical record management

### GET Medical Record
<code-group>
  <code-block label="Http" active>

  ```http request
    https://devdevice.cexup.com/api/medical-records/{{member_id/user_code}}
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
   https://devdevice.cexup.com/api/medical-records/{{member_id/user_code}}/personal
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
| type | enum(optional)[enum](/medical-record-type#medical-record)     |

### GET By Type

<code-group>
  <code-block label="Http" active>

  ```http request
   https://devdevice.cexup.com/api/medical-records/{{member_id/user_code}}/personal/filter
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
| type | enum(optional)[enum](/medical-record-type#medical-record)    |

### GET Latest
 <code-group>
  <code-block label="Http" active>

  ```http request
   https://devdevice.cexup.com/api/medical-record/{{member_id/user_code}}/latest
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

### GET Detail
 <code-group>
  <code-block label="Http" active>

  ```http request
   https://devdevice.cexup.com/api/medical-record/{{id_medical_record}}
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
| type | description |
|-----------|------------------------------------------------|
|type|medical record type[type](/medical-record-type#medical-record)|
|method|medical record method[method](/medical-record-type#medical-record)|
|value|value with type `JSON`|



### POST Personal

Registering device so the device can send data into medical record

<code-group>
  <code-block label="Http" active>

  ```http request
   https://devdevice.cexup.com/api/medical_record/personal
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

| name      | type   | description |
|-----------|--------|-------------|
| file      | File   |             |
| user_id   | String |             |
| type      | [type](/medical-record-type#medical-record)   |             |
| method    | [type](/medical-record-type#medical-record)   |             |
| note      | String |             |
| diagnosis | String |             |
| title     | String |             |


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

| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|

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

| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|

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



| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|

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

| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|

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

| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|

#### Query Params


| Name | description        |
|------|--------------------|
| size | data count to show |
| page | pagination         |
