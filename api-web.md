# eyes-world api for web

## 注册

#### 注册

* router
  * /signup

* request
```js
// POST
{
    "userName": String,
    "password": String
}
```

* respond
```js
{
    "success": Boolean
}
```

#### 验证用户名是否存在

* router
  * /signup/{userName}

* request

* respond
```js
{
    "nameUsed": Boolean
}
```

## 登录

----
### 电视获取二维码url及marker

* router
  * /login/tv/getqr  GET
  
* request


* respond
```js
    {
        "qrPath":String,
        "marker":String
    }
```

---
### 手机发送marker

* router
  * /login/phone/sendmarker  POST

* request
  * ?marker=...
  
* response
  * 200

---
###  电视登录

* router
  * /login/tv/login
  
* request
  * ?marker=...
  
* response
  *  200

---

## 景点图片评论

* router
  * /comment/{provinceName}/{cityName}/{username}/{albumId}/{photoId}  POST

* request
```js
  * ?photoComment=.....
```

* respond
```js
  * {respond:Boolean}
```

## 高校图片评论

* router
  * /comment/{provinceName}/{username}/{albumId}/{photoId}  POST

* request

  *  ?photoComment=.....


* respond
```js
  * {respond:Boolean}
```

## 上传

* router
  * /upload/{provinceName}/{cityName}/{username}  POST

* request

  * ?albumName&photoName=...&photoDesc=...


* respond
```js
  * {respond:Boolean}
```
