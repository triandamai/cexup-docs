---
title: Model
description: ''
position: 5 
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

## Intro
Dokumen ini menampung bagaiman data pada medical record disimpan. Pada `API` untuk menyimpan data `MedicalRecord` dengan menunjukkan skema request seperti berikut:
```json
[
  {
    "device_id":"11:FF",
    "member_id":"dsdfs",
    "nurse_id":"sada",
    "type":"HEART_RATE",
    "value":"80",
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
Seperti yang terlihat pada data diatas untuk menyimpan data medical record terdapat pada `value` karena setiap data memiliki perbedaan maka kita menyimpan datanya dalam bentuk json untuk contoh diatas adalah medical record yang memilik 1 value maka akan langsung diisi seperti diatas, sedangkan untuk data yang memilik lebih dari 1 value akan diubah menjadi data json. Anda dapat melihat schemanya pada dokumentasi ini.

## Skema

### Body Mass Index

| Name       | description |
|------------|-------------|
| weight   |   float         |
| height  |     float        |

Contoh:
```json
  {
    ...
    "value":{
        "weight":80,
        "height":90
    }
    ...
  }
```

### Blood Pressure

| Name       | description |
|------------|-------------|
| systole   |   int          |
| diastole  |     int        |

Contoh:
```json5
  {
    ...
    "value":{
        "systole":80,
        "diastole":90
    }
    ...
  }
```

### Blood Oxygen

| Name       | description |
|------------|-------------|
| value   |   int(%)          |

Contoh:
```json5
  {
    ...
    "value":"85"
    ...
  }
```

### Heart Rate

| Name       | description |
|------------|-------------|
| value   |   int/minute         |

Contoh:
```json
  {
    ...
    "value":70
    ...
  }
```

### Waist

| Name       | description |
|------------|-------------|
| value   |   int(CM)          |

Contoh:
```json
  {
    ...
    "value":40.5
    ...
  }
```

### Waist

| Name       | description |
|------------|-------------|
| value   |   int(CM)         |

Contoh:
```json
  {
    ...
    "value":85
    ...
  }
```

### Temperature

| Name       | description |
|------------|-------------|
| value   |   decimal(Celcius)          |

Contoh:
```json
  {
    ...
    "value":85
    ...
  }
```

### Respiration

| Name       | description |
|------------|-------------|
| value   |   int(%)          |

Contoh:
```json
  {
    ...
    "value":85
    ...
  }
```

### Pedometer

### Sleep 

## Response
Skema response pada API Medical Record

- tidak memilik akses/api key tidak ada

```json
{
    "status": "UNAUTHORIZED",
    "code": 401,
    "data": [],
    "message": "You dont have access for contact your admin for get the access"
}
```
- berhasil

```json
{
    "status": "OK",
    "code": 200,
    "data": [],
    "message": "Berhasil mengambil data"
}
```