# 获取看板中的图表信息

### URL

https://www.growingio.com/projects/{project\_uid}/dashboards/{dashboard\_id}.json

### 请求类型

GET

### 请求头参数

请参考[认证](../../authenticate/)&gt;[公共请求参数](../../authenticate/head-parameter.md)获取。

### 参数说明与示例

{% tabs %}
{% tab title="请求参数" %}
| 路径参数 | 类型 | 是否必传 | 说明 |
| :--- | :--- | :--- | :--- |
| dashboard\_id | string | 是 | 看板ID。 |
| project\_uid | string | 是 | 项目UID。 |
{% endtab %}

{% tab title="响应示例" %}
```text
{
  "id": "Dashboard Uid",
  "name": "Dashboard Name",
  "charts": [
    {
      "id": "Chart Uid",
      "name": "Chart Name",
      "createor": "Chart Creator",
      "createdAt": "Created Time"
    },
    {
      "id": "Chart Uid",
      "name": "Chart Name",
      "createor": "Chart Creator",
      "createdAt": "Created Time"
    }
  ]
}
```
{% endtab %}
{% endtabs %}

