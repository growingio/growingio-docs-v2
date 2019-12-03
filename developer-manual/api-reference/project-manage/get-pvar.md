---
description: 返回当前项目的页面级变量列表。
---

# 获取页面级变量

### URL

https://www.growingio.com /v1/api/projects/{project\_uid}/vars/pages

### 请求类型

GET

### 请求头参数

请参考[认证](../authenticate/)&gt;[公共请求参数](../authenticate/head-parameter.md)获取。

### 参数说明与示例

{% tabs %}
{% tab title="请求参数" %}
| 路径餐宿 | 类型 | 是否必传 | 说明 |
| :--- | :--- | :--- | :--- |
| project\_id | string | 是 | 项目UID。 |
{% endtab %}

{% tab title="返回示例" %}
```text
[  
  {
        "id": "id1", // 变量 uid
        "key": "test1", // 变量标识符
        "name": "测试", // 变量名称
        "mode": "DIRECT", // 变量创建方式，DIRECT: 通过接口或则打点管理创建， PAGE: 通过页面圈选创建
        "projectId": "pid1", // 项目 uid
        "createdAt": 1521446011241, // 创建时间， unix 毫秒时间戳
        "updatedAt": 1534163546862, // 最后一次更新时间， unix 毫秒时间戳
        "mappingId": 15 // 变量序号
    }
]
```
{% endtab %}
{% endtabs %}

