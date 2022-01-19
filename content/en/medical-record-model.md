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

### BODY_MASS_INDEX

| Name        | type    | unit |
|-------------|---------|------|
| weight      | decimal | kg   |
| height      | decimal | cm   |

Contoh:
```json
  {
    "value":"{\"weight\":80, \"height\":90}"
  
  }
```

### BLOOD_PRESSURE

| Name         | type | unit |
|--------------|------|------|
| systole      | int  | mmHg |
| diastole     | int  | mmHg |

Contoh:
```json5
  {
    "value":"{\"systole\":80, \"diastole\":90}"
  }
```

### BLOOD_OXYGEN

| Name     | type  | unit |
|----------|-------|------|
| value    | int   | %    |

Contoh:
```json5
  {
    "value":"85"
  }
```

### HEART_RATE

| Name     | type | unit     |
|----------|------|----------|
| value    | int  | x/minute |

Contoh:
```json
  {
    "value":"70"
  }
```

### WAIST

| Name     | type    | unit  |
|----------|---------|-------|
| value    | decimal | CM    |

Contoh:
```json
  {
    "value":"40.5"
  }
```

### TEMPERATURE

| Name    | type    | unit    |
|---------|---------|---------|
| value   | decimal | Celsius |

Contoh:
```json
  {
    "value":"85"
  }
```

### RESPIRATION

| Name   | type | unit |
|--------|------|------|
| value  | int  | %    |

Contoh:
```json
  {
    "value":"85"
  }
```

### HPHT

| Name    | type        | unit     |
|---------|-------------|----------|
| value   | bigint/long | datetime |

Contoh:
```json
  {
    "value":"652324374000"
  }
```
### EFW

| Name    | type | unit  |
|---------|------|-------|
| value   | int  | grams |

Contoh:
```json
  {
    "value":"2500"
  }
```
### FUNDAL_HEIGHT

| Name    | type    | unit |
|---------|---------|------|
| value   | decimal | CM   |

Contoh:
```json
  {
    "value":"50"
  }
```

### FHR

| Name    | type | unit     |
|---------|------|----------|
| value   | int  | x/minute |

Contoh:
```json
  {
    "value":"50"
  }
```

### HEMOGLOBIN

| Name    | type | unit                    |
|---------|------|-------------------------|
| value   | int  | milligram/dl(deciliter) |

Contoh:
```json
  {
    "value":"50"
  }
```

### URINE_PROTEIN

| Name    | type | unit |
|---------|------|------|
| value   | int  | +    |

Contoh:
```json
  {
    "value":"2"
  }
```

### REDUCTION_GLUCOSE

| Name    | type | unit |
|---------|------|------|
| value   | int  | +    |

Contoh:
```json
  {
    "value":"2"
  }
```
### MAP

| Name    | type | unit |
|---------|------|------|
| value   | int  | %    |

Contoh:
```json
  {
    "value":"2"
  }
```

### PEDOMETER
```json
{
  "value": "{\"sportCalorie\":3.0,\"sportDistance\":70.0,\"sportEndTime\":1641214800000,\"sportStartTime\":1641213000000,\"sportStep\":86}"
}

```

### SLEEP


Contoh:
```json
  {
    "value":"{\"deepSleepCount\":3,\"deepSleepTotal\":75,\"endTime\":1641172533000,\"lightSleepCount\":15,\"lightSleepTotal\":326,\"sleepData\":[{\"sleepLen\":2578,\"sleepStartTime\":1641148398000,\"sleepType\":242},{\"sleepLen\":1102,\"sleepStartTime\":1641150977000,\"sleepType\":241},{\"sleepLen\":5577,\"sleepStartTime\":1641152080000,\"sleepType\":242},{\"sleepLen\":2388,\"sleepStartTime\":1641157658000,\"sleepType\":241},{\"sleepLen\":2422,\"sleepStartTime\":1641160047000,\"sleepType\":242},{\"sleepLen\":1036,\"sleepStartTime\":1641162470000,\"sleepType\":241},{\"sleepLen\":9026,\"sleepStartTime\":1641163507000,\"sleepType\":242}],\"startTime\":1641148398000,\"wakeTime\":0}"
  }
```

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