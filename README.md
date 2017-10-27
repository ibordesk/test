# API ALONDRY
> Url prefix  : *{sitename}*/api/user

## Contents

- [Check App Version](#check-app-version--cekappver)[x] 
- [x] [Registration](#registration-register)
- [x] [Login](#login-log_in)
- [x] [Activation User](#activation-user-active_user)
- [ ] [Dashboard]
- [ ] [Order Progress]
- [ ] [Order Complete]
- [ ] [Add Order]
- [ ] [Order Process]
- [ ] [Setting Profile]

### Check App Version  :cekappver:

```
POST /check_version
```
*Request*

| Param (RAW) | Describe 							|
| -----				| -------- 							|
| application	| Aplikasi (required) 	|
| version			| Versi (required) 			|

*Response JSON*

Success %200

New app version
```json
{
    "success": "true",
    "message": "new version available",
    "data": []
} ```
No Update version
```
json
{
    "success": "true",
    "message": "no updated available",
    "data": []
}
```
---------------------------------------
### Register  
---------------------------------------
```
POST /register 
```
Request  

| Param (RAW) | Describe 											|
| -----				| -------- 											|
| nama 				| Nama user (required) 					|
| email 			| E-mail (required) 						|
| password 		| Password (required) 					|
| telp 				| telp (required) 							|



Response JSON   
Success 200
```json
{
    "success": "true",
    "message": "unverified",
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJlbWFpbCI6ImVtYWlsdGVzdGVyMTFAZXhhbXBsZS5jb20iLCJwYXNzd29yZCI6IjNhNTUxZmE5Nzk2NzVmNTJlMDkzOGIwNWFiMThiZjliN2Q3ZDMzNTdlNGFhNDI3MDFkM2M5NzRlNzk2MTJhZWZlNTIxNjg5M2Q0MzUxZDNkIiwibGFzdF9sb2dpbiI6IjIwMTctMTAtMjcgMDY6MTU6MzkifQ.LmDNWZ3zyOaepGHoOUl-UCjp1Gwazzu8u8q1PoIqQBU"
    }
}
```

Email telah terdaftar 400
```json
{
  "success"	: "false",
  "message"	: "that email is taken",
  "data" 		:	[]
}
```

Telepon telah terdaftar 400
```json
{
  "success"	: "false",
  "message"	: "this phone number already used",
  "data" 		:	[]
}
```
---------------

---------------
### Activation 
---------------
---------------

---------------
### CHECK FCM Token 
---------------
---------------

---------------
### Activation User
---------------
---------------
