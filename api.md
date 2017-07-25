视界TV端_接口文档
==========================

## 旅游景区

### 1.1 省份、城市选择

* router
  * / spots

* request
```
```

* response
```js
[{
    "province": String,
    "total": Number,
    "citys": [{
        "name": String,
        "isShown": Boolean
    }, ...]
}, ...]
```
1
### 1.2 浏览相册

* router
  * / spots / cityName

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
  * / spots / cityName

* request
```
```

* response
```js
{
    "picId": Number,
    "userName": String,
    "picName": String,
    "picDescription": String,
    "url": String,
    "isLike": Boolean,
    "likeNum": Number,
    "date": UNIX
}
```

### 1.4 上一张，下一张

* router
  * / spots / cityName

* request
```
```

* response
  * 同 1.3-response

### 1.5 点赞

* router
  * / spots / cityName

* request
```
```

* response
```
```

### 1.6 评论

* router
  * / spots / cityName

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

* router
  * / collage

* request

* response

### 2.2 浏览相册

* router
  * / collage

* request

* response
  * the same as 1.2-response

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
  * / user

* request

* response
```js
{
    "state": Boolean
}
```

### 4.2 未登录，请扫玛登录

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
  * / logout

### 4.5 我的作品

* router
  * / user / works

* response
```js
[{
    "date": UNIX,
    "url": String,
    "picId": Number,
    "albumId": Number
}, ...]
```

### 4.5 我的作品-删除


### 4.6 我的作品-上传


### 4.7 我的收藏

* router
  * / user / favorite

* response
