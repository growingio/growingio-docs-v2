# 获取圈选元素定义

### URL

https://www.growingio.com/projects/_**project\_uid**_/rules.csv

### 请求类型

GET

### 请求头参数

请参考[认证](../../authenticate/)&gt;[公共请求参数](../../authenticate/head-parameter.md)获取。

### 参数说明与示例

{% tabs %}
{% tab title="请求参数" %}
| 路径参数 | 类型 | 是否必传 | 说明 |
| :--- | :--- | :--- | :--- |
| project\_uid | string | 是 | 项目UID。 |
{% endtab %}

{% tab title="响应示例" %}
* 200：OK

{% code title="" %}
```text
ruleId,eventName,eventType
f2503720,元素_注册按钮,clck
```
{% endcode %}

* 401: Unauthorized

```text
{
  "message": "Unauthorized",
  "errors": []
}
```

* 500: Internal Server Error

```text
{
  "message": "Request timeout",
  "errors": [
    {
      "code": "request_timeout",
      "message": "Request timeout in 5000 milliseconds"
    }
  ]
}
```
{% endtab %}
{% endtabs %}



