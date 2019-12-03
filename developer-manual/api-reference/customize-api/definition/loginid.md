---
description: >-
  含义：客户从登录用户ID的视角认为有一些用户是既有用户，而不是新用户。所有GrowingIO暴露了一个接口来定义某一些登录用户ID为既有用户，并不是新用户。同时，还提供上传登录用户的注册时间，来告诉GrowingIO该用户成为新用户的时间。
---

# 既有登录用户ID上传

{% tabs %}
{% tab title="获取认证码" %}
auth的计算需要将`loginUserId`的值拼接成`keyArray，`多条使用`逗号`分隔，如上述示例中的keyArray为`abcdef,bcdefg`。Java代码示例如下：

{% code title="Java" %}
```java
/**
 * projectKeyId: 项目ID
 * secretKey: 项目私钥
 * keyArray: loginUserId用逗号拼接的字符串
*/ 
public String authToken(String projectKeyId, String secretKey, String keyArray) throws Exception {
    String message = "projectId="+projectKeyId+"&loginUserId="+keyArray;
    Mac hmac = Mac.getInstance("HmacSHA256");
    hmac.init(new SecretKeySpec(secretKey.getBytes("UTF-8"), "HmacSHA256"));
    byte[] signature = hmac.doFinal(message.getBytes("UTF-8"));
    return Hex.encodeHexString(signature);
}

```
{% endcode %}
{% endtab %}

{% tab title="接口定义" %}
### URL

https://data.growingio.com/{ai}/user/exist

### 请求类型

POST

### 请求头参数

|  名称 | 类型 | 是否必传 | 说明 |
| :--- | :--- | :--- | :--- |
| Access-Token | string | 是 | 项目公钥 |
| Content-Type | string | 是 | application/json |

### 路径参数

| 名称 | 类型 | 是否必传 | 说明 |
| :--- | :--- | :--- | :--- |
| ai | string | 是 | 项目ID。 |

### 查询参数

| 名称 | 类型 | 是否必传 | 说明 |
| :--- | :--- | :--- | :--- |
| auth | string | 是 | 针对数据生成的认证 |

### body参数

| 名称 | 类型 | 是否必传 | 说明 |
| :--- | :--- | :--- | :--- |
| loginUserId | array | 是 | 登录用户ID字符串数组 |
| register | number | 否 | 上传用户注册的时间戳 |

### body示例

```text
{
  "loginUserId": ["abcdef", "bcdefg", ...],
  "registerTime": 1514764800000
}
```

  
{% endtab %}
{% endtabs %}



