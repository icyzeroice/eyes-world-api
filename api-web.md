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
* router
  * /signin/{token}
----

* request
```js
{
    "userName": String,
    "password": String
}
```

* respond
```js

```

## 评论

* router
  * /comment

* request
```js
```

* respond
```js
```


## 上传

* router
  * /upload

* request
```js
```

* respond
```js
```
