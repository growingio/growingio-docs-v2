# 查询推广活动ID

### URL

https://www.growingio.com/api/v1/projects/_**project\_uid**_/meta/campaigns

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

{% tab title="返回参数" %}
| 名称 | 类型 | 说明 |
| :--- | :--- | :--- |
| id | string | campaign id，活动ID。 |
| name | string | 活动名称。 |
{% endtab %}

{% tab title="响应示例" %}
```text
[
  {
    "id": "gnPNkoWA",
    "name": "双十一推广"
  },
  {
    "id": "La9BwRne",
    "name": "美丽星辰"
  }
]
```
{% endtab %}
{% endtabs %}

