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
true---可以使用
false---不可用使用，已经重名
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

### 添加图片评论

* router
  * /spotsComment/{provinceName}/{cityName}/{albumId}/{photoId}  POST

* request
```js
  * ?photoComment=.....
```

* respond
```js
  * {respond:Boolean}
```

### 是否可删除图片评论（用户自己发的评论才可以删除）

* router
  * /spotsComment/{provinceName}/{cityName}/{albumId}/{photoId}/{commentId}/deletable
  
* respond
```js
  * {respond:Boolean} 
```
true---可删除
false---不可删除

### 删除图片评论
* router
  * /spotsComment/{provinceName}/{cityName}/{albumId}/{photoId}/{commentId}/delete
  
* respond
```js
  * {respond:Boolean}
```



## 高校图片评论

### 添加图片评论

* router
  * /collegeComment/{provinceName}/{albumId}/{photoId}  POST

* request

  *  ?photoComment=.....


* respond
```js
  * {respond:Boolean}
```
### 是否可删除图片评论（用户自己发的评论才可以删除）

* router
  * /collegeComment/{provinceName}/{albumId}/{photoId}/{commentId}/deletable
  
* respond
```js
  * {respond:Boolean} 
```
true---可删除
false---不可删除


### 删除图片评论

* router
  * /collegeComment/{provinceName}/{albumId}/{photoId}/{commentId}/delete  
  
* respond
```js
  * {respond:Boolean}
```


## 上传

### 景点图片上传

* router
  * /upload/{provinceName}/{cityName}/{username}  POST

* request

  * ?albumName=...&photoName=...&photoDesc=...


* respond
```js
  * {respond:Boolean}
```
### 高校图片上传

* router
  * /upload/{provinceName}/{username}  POST

* request

  * ?albumName=...&photoName=...&photoDesc=...


* respond
```js
  * {respond:Boolean}
```



