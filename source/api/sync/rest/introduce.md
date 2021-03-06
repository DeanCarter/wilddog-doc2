
title: REST API 简介

---

我们可以使用任意的Wilddog应用的URL作为REST的结束点，我们只需要在URL的结尾处加上`.json`然后发送HTTPS请求即可。 HTTPS是必须的，Wilddog只会响应加密数据，所以你的数据是保证安全的。

## 请求类型

### GET

**说明**

通过HTTP发送GET请求就可以读取数据库中的数据 请求成功将会返回200 OK状态码。响应中会包含要查询的数据。

**示例**

```
curl 'https://samplechat.wilddogio.com/users/jack/name.json'

```

**返回值**

```
{ "first": "Jack", "last": "Sparrow" }

```

---

### PUT

**说明**

我们可以使用 `PUT` 请求写入数据

**示例**

```
curl -X PUT -d '{ "first": "Jack", "last": "Sparrow" }' \
  'https://samplechat.wilddogio.com/users/jack/name.json'

```

**返回值**

```
{ "first": "Jack", "last": "Sparrow" }

```

---

### POST

**说明**

要实现js中`push()`方法类似的功能，我们可以使用`POST`请求

**示例**

```
curl -X POST -d '{"user_id" : "jack", "text" : "Ahoy!"}' \
  'https://samplechat.wilddogio.com/message_list.json'

```

**返回值**

```
{ "name": "-INOQPH-aV_psbk3ZXEX" }

```

---

### PATCH

**说明**

我们可以使用`PATCH`请求来更新指定位置的数据而不覆盖其他已有的数据。`PATCH`请求中指定的节点数据会被覆盖，没有提到的节点不会被删除。该功能与js中的`update()`方法类似。

**示例**

```
curl -X PATCH -d '{"last":"Jones"}' \
 'https://samplechat.wilddogio.com/users/jack/name/.json'

```

**返回值**

```
{ "last": "Jones" }

```

---

### DELETE

**说明**

我们可以使用`DELETE`请求来删除数据。

**示例**

```
curl -X DELETE \
  'https://samplechat.wilddogio.com/users/jack/name/last.json'

```

**返回值**

请求成功将会返回200 OK 状态码。响应中会包含空的 JSON

---

### 方法覆盖

**说明**

如果我们发出REST调用的浏览器不支持上面的方法，我们可以覆盖请求方法，发送`POST`请求通过请求头中的`X-HTTP-Method-Override`设置要覆盖的方法。

**示例**

```
curl -X POST -H "X-HTTP-Method-Override: DELETE" \
  'https://samplechat.wilddogio.com/users/jack/name/last.json'

```

我们也可以使用`x-http-method-override`查询参数：

```
curl -X POST \
  'https://samplechat.wilddogio.com/users/jack/name/last.json?x-http-method-override=DELETE'

```

**返回值**

请求成功将会返回200 OK 状态码。响应中会包含空的JSON
