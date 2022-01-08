---
title: Database
description: ''
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

Database for medical record API, we implement Medical Record api using [Spring boot](https://spring.io)
and [Spring Data JPA](https://spring.io/projects/spring-data-jpa) that why the schema have some different type example for `enum` in `JPA` become `integer`.

## Schema
This schema is the latest for medical record we use today and updated when the schema changed.
<img src="medical-record-db-schema-2022-01-08.png">


### Schema v1(Base version)
- Table Api Access

| Name        | type         | description |
|-------------|--------------|-------------|
| id          | bigint       |             |
| api_key_id  | varchar(255) |             |
| hospital_id | varchar(255) |             |
| created_at  | bigint       |             |
| updated_at  | bigint       |             |

- Table Api Key

| Name        | type         | description |
|-------------|--------------|-------------|
| hospital_id | bigint       |             |
| value       | varchar(255) |             |
| created_at  | bigint       |             |
| updated_at  | bigint       |             |

- Table Device

| Name          | type         | description |
|---------------|--------------|-------------|
| id            | bigint       |             |
| device_holder | varchar(255) |             |
| device_name   | varchar(255) |             |
| device_mac    | varchar(255) |             |
| device_type   | enum         |             |
| created_at    | bigint       |             |
| updated_at    | bigint       |             |

- Table Hospital

| Name       | type         | description |
|------------|--------------|-------------|
| id         | bigint       |             |
| name       | varchar(255) |             |
| email      | varchar(255) |             |
| domain     | varchar(255) |             |
| address    | varchar(255) |             |
| phone      | varchar(255) |             |
| region     | varchar(255) |             |
| created_at | varchar(255) |             |
| updated_at | bigint       |             | 
| deleted_at | bigint       |             |

- Table Medical Record

| Name        | type         | description |
|-------------|--------------|-------------|
| id          | bigint       |             |
| type        | enum         |             |
| member_id   | varchar(255) |             |
| nurse_id    | varchar(255) |             |
| hospital_id | varchar(255) |             |
| method      | enum         |             |
| value       | json         |             |
| assets      | varchar(255) |             |
| device_id   | varchar(255) |             |
| created_at  | varchar      |             |
| updated_at  | bigint       |             | 

- Table User

| Name       | type         | description |
|------------|--------------|-------------|
| id         | bigint       |             |
| username   | varchar(255) |             |
| password   | varchar(255) |             |
| level      | varchar(255) |             |
| created_at | varchar(255) |             |
| updated_at | bigint       |             | 



