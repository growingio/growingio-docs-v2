---
description: GrowingIO 根据付费版本设定不同的埋点事件和维度的限额，通过此接口获取您项目的限额。
---

# 获取埋点数量限额

### URL

https://www.growingio.com /v1/api/projects/_**project\_uid**_/vars/quotas

### 请求类型

GET

### 请求头参数

请参考[认证](../authenticate/)&gt;[公共请求参数](../authenticate/head-parameter.md)获取。

### 参数说明与示例

{% tabs %}
{% tab title="参数说明" %}
| 路径参数 | 类型 | 是否必传 | 说明 |
| :--- | :--- | :--- | :--- |
| project\_id | string | 是 | 项目UID。 |
{% endtab %}

{% tab title="返回示例" %}
200：OK

```text
{
    "event": 50000, // 打点事件限额
    "var": 100, // 事件级变量限额
    "pvar": 50, // 页面级变量限额
    "ppl": 50000 // 登录用户变量限额
}
```
{% endtab %}
{% endtabs %}

