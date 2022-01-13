---
title: Type
description: ''
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

## Why?
Initially we use integer for different type data example in medical record we use type for grouping what kind the data is but using integer making 
other developer struggling with knowing what the type, that why we choose `enum`.

## Data Type

### Medical Record

#### Medical Record Type
| Name               | description |
|--------------------|-------------|
| TEMPERATURE        |             |
| HEART_RATE         |             |
| BLOOD_PRESSURE     |             |
| BODY_MASS_INDEX    |             |
| WAIST              |             |
| BLOOD_OXYGEN       |             |
| STETHOSCOPE        |             |
| ELECTROCARDIOGRAPH |             |
| PEDOMETER          |             |
| SLEEP              |             |
| RESPIRATION        |             |
| RONTGEN            |             |
| LABTEST            |             |
| MEDICINE           |             |
| NOTE               |             |

#### Medical Record Method
| Name       | description |
|------------|-------------|
| AUTOMATIC  |             |
| MANUAL     |             |
| PERSONAL   |             |


### Device

#### Device type
| Name       | description |
|------------|-------------|
| CONSUMER   |             |
| CORPORATE  |             |

### Hospital

| Name       | description |
|------------|-------------|
| CONSUMER   |             |
| CORPORATE  |             |
## Schema
### Medical Record
1. Body Mass Index

| Name       | description |
|------------|-------------|
| weight   |   float          |
| height  |     float        |

2. Blood Pressure

| Name       | description |
|------------|-------------|
| systole   |   int          |
| diastole  |     int        |

3. Blood Oxygen

| Name       | description |
|------------|-------------|
| spo2   |   int          |