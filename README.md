# API ALONDRY
> Url prefix  : *{sitename}*/api/user

## Contents

- [x] [Check App Version](#check-app-version)
- [x] [Registration User](#registration-user)
- [x] [Login User](#login-user)
- [x] [Activation User](#activation-user)
- [x] [Dashboard](#dashboard)
- [x] [Update Profile](#update-profile)
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
    "message": "Registration success",
    "data": [
        {
            "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJlbWFpbCI6ImVtYWlsdGVzdGVyM0BleGFtcGxlLmNvbSIsInBhc3N3b3JkIjoidGVzdGVyMyIsImxhc3RfbG9naW4iOiIyMDE3LTEwLTI4IDIyOjIxOjE3In0.VuUsYAP3qPMVBH7Fzbf_p0EQv1R9wThbX3PN7tK3nxo"
        }
    ]
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

### Activation User
> POST */user_activation*

***Request: ***  
*Need header token

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

- **Authentikasi token gagal** `STATUS:400`
```json
{
  "success"	: "false",
  "message"	: "Authentication token failed",
  "data" 	: []
}
```

### Login User
> POST */login*

***Request: ***  
*Need header auth

| PARAM (RAW) | Describe 											|
| -----				| -------- 											|
| email 				| Email User (required) 					|
| password 			| Password User (required) 						|



***Response:***   
- **Login Berhasil, User Belum Terverifikasi** `STATUS:200`
```json
{
    "success": "true",
    "message": "unverified",
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJlbWFpbCI6ImVtYWlsdGVzdGVyMTFAZXhhbXBsZS5jb20iLCJwYXNzd29yZCI6IjNhNTUxZmE5Nzk2NzVmNTJlMDkzOGIwNWFiMThiZjliN2Q3ZDMzNTdlNGFhNDI3MDFkM2M5NzRlNzk2MTJhZWZlNTIxNjg5M2Q0MzUxZDNkIiwibGFzdF9sb2dpbiI6IjIwMTctMTAtMjcgMDY6MTU6MzkifQ.LmDNWZ3zyOaepGHoOUl-UCjp1Gwazzu8u8q1PoIqQBU"
    }
}
```

- **Login Berhasil, User Sudah Terverifikasi** `STATUS:200`
```json
{
    "success": "true",
    "message": "verified",
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJlbWFpbCI6ImVtYWlsdGVzdGVyMTFAZXhhbXBsZS5jb20iLCJwYXNzd29yZCI6IjNhNTUxZmE5Nzk2NzVmNTJlMDkzOGIwNWFiMThiZjliN2Q3ZDMzNTdlNGFhNDI3MDFkM2M5NzRlNzk2MTJhZWZlNTIxNjg5M2Q0MzUxZDNkIiwibGFzdF9sb2dpbiI6IjIwMTctMTAtMjcgMDY6MTU6MzkifQ.LmDNWZ3zyOaepGHoOUl-UCjp1Gwazzu8u8q1PoIqQBU"
    }
}
```

- **Authentikasi token gagal** `STATUS:400`
```json
{
  "success"	: "false",
  "message"	: "Authentication token failed",
  "data" 	: []
}
```

### Dasboard
> POST */dashboard*

***Request: ***  
*Need header token
*No parameter

***Response:***   
- **Autentikasi berhasil** `STATUS:200`
```json
{
    "user": {
        "id": "1",
        "nama": "tester1",
        "password": "tester1",
        "email": "emailtester1@example.com",
        "telp": "085700000001",
        "tgl_lahir": null,
        "tempat_lahir": null,
        "alamat": null,
        "created_at": "2017-10-28 22:16:24",
        "status": "0",
        "status_user": "nonaktif"
    },
    "banner": [
        {
            "image": "sitbanner3.jpg"
        },
        {
            "image": "sitbanner1.jpg"
        }
    ],
    "cs": {
        "telp": "085604507383"
    }
}{
  "success"	: "true",
  "message"	: "user verificated",
  "data" 	: []
}
```

- **Authentikasi gagal** `STATUS:400`
```json
{
  "success"	: "false",
  "message"	: "Authentication token failed",
  "data" 	: []
}
```

### Update Profile
> POST */update_profile*

***Request: ***  
*Need header token
***Parameter menyesuaikan data apa yg diubah***
| Param (RAW) | Describe 											|
| -----				| -------- 											|
| nama 				| Nama user (optional) 					|
| email 			| E-mail (optional) 						|
| password 		| Password (optional) 					|
| telp 				| telp (optional) 							|
| tgl_lahir 		| tanggal lahir (optional) 					|
| tempat_lahir 				| tempat_lahir (optional) 							|
| alamat 				| alamat (optional) 							|

***Response:***   
- **Profile berhasil dirubah** `STATUS:200`
```json
{
    "success": "true",
    "message": "Successfully updating profile",
    "data": {
        "user": {
            "id": "1",
            "nama": "tester1",
            "password": "tester1",
            "email": "emailtester1@example.com",
            "telp": "085694507293",
            "tgl_lahir": null,
            "tempat_lahir": null,
            "alamat": null,
            "created_at": "2017-10-28 22:16:24",
            "status": "0",
            "status_user": "nonaktif"
        },
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJlbWFpbCI6bnVsbCwicGFzc3dvcmQiOm51bGwsImxhc3RfbG9naW4iOm51bGx9.Dw_5nu5ZY6mppyUjslFq8PoxnrwgJw_WWIsVou7mKCo"
    }
}
```

- **Profile tidak berubah** `STATUS:400`
```json
{
  "success"	: "false",
  "message"	: "Nothing changed",
  "data" 	: []
}
```
