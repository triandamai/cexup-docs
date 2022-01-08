---
title: Medical Record Api 
description: ''
position: 1 
category: API
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

## Device
Feature device IoT management:

### GET list device

Getting devices that has registered into database Cexup

<code-group>
  <code-block label="cURL" active>

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
---

| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|


#### Query Params
---

| Name | description        |
|------|--------------------|
| size | data count to show |
| page | pagination         |

### POST add device

Registering device so the device can send data into medical record

<code-group>
  <code-block label="cURL" active>

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
---

| x-api-key | MTYzNTEzMDIzNDY0MA==16351302346401637558061370 |
|-----------|------------------------------------------------|


#### Body
---
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