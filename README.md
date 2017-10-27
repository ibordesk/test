# API ALONDRY
> Url prefix  : *{sitename}*/api/user

## Contents

- [x] [Check App Version](#check-app-version)
- [x] [Registration User](#registration-user)
- [x] [Login User](#login-user)
- [x] [Activation User](#activation-user)
- [ ] [Dashboard]
- [ ] [Order Progress]
- [ ] [Order Complete]
- [ ] [Add Order]
- [ ] [Order Process]
- [ ] [Setting Profile]

-----------

### Check App Version

> POST */check_version*

***Request:***

| Param (RAW) | Describe 							|
| -----				| -------- 							|
| application	| Aplikasi (required) 	|
| version			| Versi (required) 			|

***Response:***

**New app version** `STATUS:200`
```json
{
    "success"   : "true",
    "message"   : "new version available",
    "data"      : []
} 
```

**No Update version** `STATUS:200`
```
json
{
    "success"   : "true",
    "message"   : "no updated available",
    "data"      : []
}
```

-------

### Registration User 

> POST */register*

***Request:***  

| Param (RAW) | Describe 											|
| -----				| -------- 											|
| nama 				| Nama user (required) 					|
| email 			| E-mail (required) 						|
| password 		| Password (required) 					|
| telp 				| telp (required) 							|



***Response:***   
- **Registrasi Berhasil** `STATUS:200`
```json
{
    "success": "true",
    "message": "unverified",
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJlbWFpbCI6ImVtYWlsdGVzdGVyMTFAZXhhbXBsZS5jb20iLCJwYXNzd29yZCI6IjNhNTUxZmE5Nzk2NzVmNTJlMDkzOGIwNWFiMThiZjliN2Q3ZDMzNTdlNGFhNDI3MDFkM2M5NzRlNzk2MTJhZWZlNTIxNjg5M2Q0MzUxZDNkIiwibGFzdF9sb2dpbiI6IjIwMTctMTAtMjcgMDY6MTU6MzkifQ.LmDNWZ3zyOaepGHoOUl-UCjp1Gwazzu8u8q1PoIqQBU"
    }
}
```

- **Email tidak bisa digunakan** `STATUS:400`
```json
{
  "success"	: "false",
  "message"	: "that email is taken",
  "data" 	: []
}
```

- **Telepon tidak bisa digunakan** `STATUS:400`
```json
{
  "success"	: "false",
  "message"	: "this phone number already used",
  "data" 	: []
}
```

### Login User
> POST */login*

***Request: ***  
*Need header auth

| HEADER (BASIC) | Describe 											|
| -----				| -------- 											|
| email 				| Email User (required) 					|
| password 			| Password User (required) 						|



***Response:***   
- **Login Berhasil** `STATUS:200`
```json
{
    "success": "true",
    "message": "unverified",
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJlbWFpbCI6ImVtYWlsdGVzdGVyMTFAZXhhbXBsZS5jb20iLCJwYXNzd29yZCI6IjNhNTUxZmE5Nzk2NzVmNTJlMDkzOGIwNWFiMThiZjliN2Q3ZDMzNTdlNGFhNDI3MDFkM2M5NzRlNzk2MTJhZWZlNTIxNjg5M2Q0MzUxZDNkIiwibGFzdF9sb2dpbiI6IjIwMTctMTAtMjcgMDY6MTU6MzkifQ.LmDNWZ3zyOaepGHoOUl-UCjp1Gwazzu8u8q1PoIqQBU"
    }
}
```
   
- **Login Gagal** `STATUS:401`
```
json
```

---------------

### Activation User
> POST */user_activation*

***Request: ***  
*Need header auth

| PARAM (RAW) | Describe 											|
| -----				| -------- 											|
| code 				| Code from mail (required) 					|



***Response:***   
- **Aktivasi Berhasil** `STATUS:200`
```json
{
  "success"	: "true",
  "message"	: "user verificated",
  "data" 	: []
}
```
   
- **Aktivasi Gagal** `STATUS:400`
```json
{
  "success"	: "false",
  "message"	: "verification user failed",
  "data" 	: []
}
```
