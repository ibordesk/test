# API DIJUALCEPAT
> Url prefix  : *{sitename}*/api/user

## Contents

*default*

- [ ] [Home](#home)
- [ ] [Category](#category)
- [ ] [Contact Us](#contact-us)
- [ ] [About Us](#about-us)
- [ ] [Detail Product](#detail-product)
- [ ] [Registration User](#registration-user)
- [ ] [Login User](#login-user)


*saat user login*
- [ ] [Home](#home)
- [ ] [Detail Product](#detail-product)
- [ ] [Contact Us](#contact-us)
- [ ] [About Us](#about-us)
- [ ] [Terms Condition](#terms-condition)
- [ ] [Profile User](#profile-user)
- [ ] [Product User](#product-user)
- [ ] [Balance User](#balance-user)
- [ ] [Topup User](#topup-user)
- [ ] [Sell Product](#sell-product)
- [ ] [Favorite Product](#favorite-product)
- [ ] [Message User](#message-user)
-----------


### Home 


***Request:***  
> GET */home*

***Response:***   

- **Response Berhasil** `STATUS:200`
***data yg ditampilkan berupa 4 iklan premium {premium}, 4 iklan teratas {top}, dan banner***
```json
{
    "success": "true",
    "message": "Berhasil mengakses home",
    "data": [
      "article":[
        {
          "id_product":"1",
          "title_product":"Product Title",
          "price_product":"100000",
          "image_product":"http://dijualcepat.com/product/image1.jpg",
          "type_product":"premium"
        },
        {
          "id_product":"2",
          "title_product":"Product Title",
          "price_product":"100000",
          "image_product":"http://dijualcepat.com/product/image2.jpg",
          "type_product":"premium"
        },
        {
          "id_product":"3",
          "title_product":"Product Title",
          "price_product":"100000",
          "image_product":"http://dijualcepat.com/product/image3.jpg",
          "type_product":"premium"
        },
        {
          "id_product":"4",
          "title_product":"Product Title",
          "price_product":"100000",
          "image_product":"http://dijualcepat.com/product/image4.jpg",
          "type_product":"premium"
        },
        {
          "id_product":"5",
          "title_product":"Product Title",
          "price_product":"100000",
          "image_product":"http://dijualcepat.com/product/image5.jpg",
          "type_product":"top"
        },
        {
          "id_product":"6",
          "title_product":"Product Title",
          "price_product":"100000",
          "image_product":"http://dijualcepat.com/product/image6.jpg",
          "type_product":"top"
        },
        {
          "id_product":"7",
          "title_product":"Product Title",
          "price_product":"100000",
          "image_product":"http://dijualcepat.com/product/image7.jpg",
          "type_product":"top"
        },
        {
          "id_product":"8",
          "title_product":"Product Title",
          "price_product":"100000",
          "image_product":"http://dijualcepat.com/product/image8.jpg",
          "type_product":"top"
        }
      ],
      "banner":[
        {"image":"banner_promo1.jpg"},
        {"image":"banner_promo1.jpg"}
      ]  
    ]
}
```

- **Response Gagal** `STATUS:400`
```json
{
  "success" : "false",
  "message" : "Tidak dapat mengakses home",
  "data"  : []
}
```



### Detail Product 

***Request:***  
> POST */detail_product*

| PARAM (RAW) | Describe                      |
| -----       | --------                      |
| id_product  | id_product (required)         |

***Response:***
- **Response Berhasil** `STATUS:200`
***data yang dikirim berupa list category dan subkategori***
```json
{
  "success" : "true",
  "message" : "Berhasil mengakses Detail Produk",
  "data"  : 
    {
      "id_product":"1",
      "title_product":"Nama Kategori",
      "desc_product":"Lorem ipsum dolor sit amet",
      "image_product":[
          {"image":"http://dijualcepat.com/product/image1.jpg"},
          {"image":"http://dijualcepat.com/product/image2.jpg"}
      ],
      "datepost_product":"2017-12-12",
      "condition_product":"new",
      "code_product":"USJ891",
      "viewed_product":"2000",
      "contacted_product":"10",
      "location_product":"address product",
      "lat_product":"maps latitude product",
      "long_product":"maps longitude product",
      "id_user":"2",
      "name_user":"name user",
      "datemember_user":"2017-12-12",
      "image_user":"http://dijualcepat.com/user/image.jpg",
      "comment_product":[
        {
          "id_user":"1",
          "image_user":"http://dijualcepat.com/user/image1.jpg",
          "comment_user":"lorem ipsum dolor sit amet",
        },
        {
          "id_user":"2",
          "image_user":"http://dijualcepat.com/user/image2.jpg",
          "comment_user":"lorem ipsum dolor sit amet",
        },
      "related_product":[
        {
          "id_product":"1",
          "image_product":"http://dijualcepat.com/product/image1.jpg",
          "title_product":"Title Product",
          "price_product":"20000"
        },
        {
          "id_product":"1",
          "image_product":"http://dijualcepat.com/product/image2.jpg",
          "title_product":"Title Product",
          "price_product":"20000"
        }
      ]
    }
}
```
- **Response Gagal** `STATUS:400`   
```json
{
  "success" : "false",
  "message" : "Gagal mengakses Detail Produk",
  "data"  : []
}
```


### Category 

***Request:***  
> GET */category*

***Response:***
- **Response Berhasil** `STATUS:200`
***data yang dikirim berupa list category dan subkategori***
```json
{
  "success" : "true",
  "message" : "Berhasil mengakses Kategori",
  "data"  : [
    {
      "id_category":"1",
      "title_category":"Nama Kategori",
      "icon_category":"Icon.jpg",
      "subcategory":[]
    },
    {
      "id_category":"2",
      "title_category":"Nama Kategori",
      "icon_category":"Icon.jpg",
      "subcategory":[
        {
        "id_subcategory":"3",
        "title_subcategory":"Nama Kategori",
        "icon_subcategory":"Icon.jpg"
        },
        {
        "id_subcategory":"4",
        "title_subcategory":"Nama Kategori",
        "icon_subcategory":"Icon.jpg"
        }
      ]
    },
  ]
}
```
- **Response Gagal** `STATUS:400`   
```json
{
  "success" : "false",
  "message" : "Gagal mengakses Kategori",
  "data"  : []
}
```

### Contact Us 

***Request:***  
> GET */contact_us*

***Response:***
- **Response Berhasil** `STATUS:200`
***data yang dikirim berupa list category dan subkategori***
```json
{
  "success" : "true",
  "message" : "Berhasil mengakses Contact Us",
  "data"  : 
    {
      "content":"content contact us"
    }
}
```
- **Response Gagal** `STATUS:400`   
```json
{
  "success" : "false",
  "message" : "Gagal mengakses Contact Us",
  "data"  : []
}
```

### About Us 

***Request:***  
> GET */about_us*

***Response:***
- **Response Berhasil** `STATUS:200`
***data yang dikirim berupa list category dan subkategori***
```json
{
  "success" : "true",
  "message" : "Berhasil mengakses About Us",
  "data"  : 
    {
      "content":"content about us"
    }
}
```
- **Response Gagal** `STATUS:400`   
```json
{
  "success" : "false",
  "message" : "Gagal mengakses About Us",
  "data"  : []
}
```


-----------------------------

### Registration User 

> POST */register*

***Request:***  

| Param (RAW) | Describe                      |
| -----       | --------                      |
| nama        | Nama user (required)          |
| email       | E-mail (required)             |
| password    | Password (required)           |
| telp        | telp (required)               |



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
  "success" : "false",
  "message" : "that email is taken",
  "data"  : []
}
```

- **Telepon tidak bisa digunakan** `STATUS:400`
```json
{
  "success" : "false",
  "message" : "this phone number already used",
  "data"  : []
}
```

### Login User
> POST */login*

***Request: ***  
*Need header auth

| PARAM (RAW) | Describe                      |
| -----       | --------                      |
| email         | Email User (required)           |
| password      | Password User (required)            |



***Response:***   
- **Login Berhasil** `STATUS:200`
```json
{
    "success": "true",
    "message": "Login success",
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJlbWFpbCI6ImVtYWlsdGVzdGVyMTFAZXhhbXBsZS5jb20iLCJwYXNzd29yZCI6IjNhNTUxZmE5Nzk2NzVmNTJlMDkzOGIwNWFiMThiZjliN2Q3ZDMzNTdlNGFhNDI3MDFkM2M5NzRlNzk2MTJhZWZlNTIxNjg5M2Q0MzUxZDNkIiwibGFzdF9sb2dpbiI6IjIwMTctMTAtMjcgMDY6MTU6MzkifQ.LmDNWZ3zyOaepGHoOUl-UCjp1Gwazzu8u8q1PoIqQBU"
    }
}
```

- **Authentikasi token gagal** `STATUS:400`
```json
{
  "success" : "false",
  "message" : "Authentication token failed",
  "data"  : []
}
```
