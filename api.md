视界TV端_接口文档
==========================

## 旅游景区

### 1.1 省份、城市选择

#### 省份信息

* router
  * /provinces/cities

* request
```
```

* response
```js
[{
    "provinceName": String,
    "spotNum": Number,
	"collegeNum": Number
},
...]
```
例子：
```js
[{"provinceName":"广东","spotNum":1,"collegeNum":1},{"provinceName":"广西","spotNum":0,"collegeNum":0}]
```
#### 城市信息
* router
  * /provinces/cities/{provinceName}

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
  * /provinces/cities/{provinceName}/{cityName}/spots

* request
```
```

* response
```js
[{
    "albumId": Number,
    "albumName": String,
    "visitAmount": Number,
    "likeAmount": Number,
    "url": String
}, ...]
```

### 1.3 浏览图片

albumId，photoId从0开始计数

* router
  * /provinces/cities/{provinceName}/{cityName}/spots/{albumId}/{photoId}
  * /provinces/cities/广东/佛山/spots/0/0     第一个相册的第一张图片
  * /provinces/cities/广东/佛山/spots/0/1     第一个相册的第二张图片


* 第一次请求图片

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
    "like":Boolean,
    "likeAmount":Number,
    "createTime":Number
    "last": Boolean
}
```


like:true---还没点赞

like:false---已经点赞

last:true---是相册的最后一张照片

last:false---不是相册的最后一张照片


```js
例子
{"photoId":6,
"username":"Mike",
"photoName":"abcd--1234567",
"photoDescription":"666",
"url":"/upload/广东/潮州/Mike/abcd%%1501641406355",
"like":true,
"likeAmount":1,
"createTime":0,
"last":false}
```

* 第二次请求图片字节流

* router
  * /upload/{provinceName}/{cityName}/{username}/{photoName}
  * /upload/广东/潮州/Mike/abcd--1234567

* request

* respose
字节流


* 作用


获取一album里所有照片的id按顺序形成数组


### 1.4 上一张，下一张

* router
  * /provinces/cities/{provinceName}/{cityName}/spots/{albumId}/{photoId}

* request
```
```

* response
  * 同 1.3-response

* 上一张下一张通过photoId加一减一实现

### 1.5 景点图片点赞

* router
  * /provinces/cities/{provinceName}/{cityName}/spots/{albumId}/{photoId}/like

* request


* response
```
{
    "state":Boolean
}
```

true---显示已点赞
false---显示未点赞

### 1.6 获取景点评论

* router
  * /provinces/cities/{provinceName}/{cityName}/spots/{albumId}/{photoId}/comment

* request

* response
```js
[{
	"commentId":Integer,
    "userName": String,
    "comment": String,
    "modificationTime": Number
}, ...]
```

```js
[{"commentId":8,
"username":"Mike",
"content":"123121414",
"modificationTime":2017}]
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
	"provinceName": String,
    "spotNum": Number,
	"collegeNum": Number
},
...]
```

#### 高校选择

* router
  * /provinces/college/{provinceName}

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


### 2.2 浏览高校图片

* router
  * /provinces/college/{provinceName}/{albumId}/{photoId}
  * /provinces/college/广东/0/0     第一个相册的第一张图片
  * /provinces/college/广东/0/1    第一个相册的第二张图片
  * 这里photoId默认值为0
  * 前端自己判断是否能点击上一张下一张

* request
```
```

* response
  * 同 1.3-response


### 2.3 高校图片点赞

* router
  * /provinces/college/{provinceName}/{albumId}/{photoId}/like

* request


* response
```
{
    "state":Boolean
}
```
true---显示已点赞
false---显示未点赞

### 2.4 获取高校评论

* router
  * /provinces/college/{provinceName}/{albumId}/{photoId}/comment

* request

* response
```js
[{
	"commentId":Integer,
    "userName": String,
    "comment": String,
    "modificationTime": Number
}, ...]
```
```js
例子：
[{"commentId":9,
"username":"Mike",
"content":"评论内容1",
"modificationTime":2017},
{"commentId":10,
"username":"Liky",
"content":"评论内容2",
"modificationTime":2017}]
```


## 最新推荐

### 3.1 轮播图

* router
  * /lastest

* response
  * 同 1.2-response

### 3.2 推荐相册

* router
  * /lastest

* response
  * 同 1.3-response

## 用户管理

### 4.1 登录状态判断

* router
  * /user

* request
  * cookie：
  
* response
```js
{
    "state":Boolean,
    "username": String //state = 1 时才返回
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

* 要有过期时间

### 4.3 已经登录

* 跳到 4.1 重新验证

### 4.4 退出

* router
  * /logout

### 4.5 我的作品

* router
  * /user/works/{userName}

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

  * /user/works/{userName}/delete/{albumId}/{photoName}

### 4.6 我的作品-上传

* response
  * 返回二维码，及token、链接

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



## 删除图片

* router
  * /upload/{provinceName}/{cityName}/{username}  POST

* request

  * ?photoName=...&url=...


* respond
```js
  * {respond:Boolean}
```
