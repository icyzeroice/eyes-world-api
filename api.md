视界TV端_接口文档
==========================

## 旅游景区

### 1.1 省份、城市选择

#### 省份信息

* router
  * /provinces

* request
```
```

* response
```js
[{
    "province": String,
    "citiesNum": Number,
},
...]
```
#### 城市信息
* router
  * /cities/{provinceName}
  
* request
  * 
  
* response
```js
[{
    "city": String,
    "albumNum": Number,
},
...]
```


### 1.2 浏览相册

* router
  * /spots/{cityName}

* request
```
```

* response
```js
[{
    "albumId": Number,
    "name": String,
    "visited": Number,
    "likeNum": Number,
    "url": String
}, ...]
```

### 1.3 浏览图片

* router
  * / spots /{albumId}

* request
```
```

* response
```js
[
    {"photoId":Number},
    {"photoId":Number},
    ...
]
```
* 作用\
获取一album里所有照片的id按顺序形成数组

### 1.4 上一张，下一张

* router
  * / spots /{albumId}/{photoId}

* request
```
```

* response
```js
{
    "photoId":Number,
    "username":String,
    "photoName":String,
    "photoDescription":String,
    "url":String,
    "isLike":Boolean,
    "likeNum":Number,
    "time":Number
}
```

### 1.5 点赞

* router
  * /like/{albumId}/{photoId}

* request
```
```

* response
```
{
    "isSuccessful":Boolean
}
```

### 1.6 获取评论

* router
  * /comment/{photoId}

* request

* response
```js
[{
    "userName": String,
    "comment": String,
    "date": UNIX
}, ...]
```

## 高校景观

### 2.1 省份选择
#### 省份选择
* router
  * /provinces/collage

* request

* response
```js
[{
    "province": String,
    "collegesNum": Number,
},
...]
```

#### 高校选择

* router
  * /college/{provinceName}
  
* request
  * 
  
* response
```js
[{
    "college": String,
    "albumId": Number,
    "name": String,
    "visited": Number,
    "likeNum": Number,
    "url": String
},
...]
```


### 2.2 浏览图片

* router
  * /spots/{albumId}

* request
```
```

* response
```js
[
    {"photoId":Number},
    {"photoId":Number},
    ...
]
```

### 2.3 上一张，下一张

* router
  * / spots /{albumId}/{photoId}

* request
```
```

* response
```js
{
    "photoId":Number,
    "username":String,
    "photoName":String,
    "photoDescription":String,
    "url":String,
    "isLike":Boolean,
    "likeNum":Number,
    "time":Number
}
```

## 最新推荐

### 3.1 轮播图

* router
  * / lastest

* response

### 3.2 推荐相册

* router
  * / lastest

## 用户管理

### 4.1 登录状态判断

* router
  * /user

* request

* response
```js
{
    "state":Boolean,
    "username": String
}
```

### 4.2 未登录，请扫玛登录
???
* response
```js
{
    "QRUrl": String
}
```

### 4.3 已经登录

* 

### 4.4 退出

* router
  * /logout

### 4.5 我的作品

* router
  * / user / works

* response
```js
[{
    "date": UNIX,
    "url": String,
    "photoId": Number,
    "photoName":String,
    "albumId": Number,
    "albumName":String
}, ...]
```

### 4.5 我的作品-删除


### 4.6 我的作品-上传
返回二维码，及token
### 4.7 我的收藏

* router
  * /user/favorite/{userId}

* response
```js
[{
    "date": UNIX,
    "url": String,
    "photoId": Number,
    "photoName":String,
    "albumId": Number,
    "albumName":String
}, ...]
```