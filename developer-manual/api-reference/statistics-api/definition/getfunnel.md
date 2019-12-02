# 获取漏斗分析数据

### URL

https://www.growingio.com/v2/projects/_**project\_uid**_/funnels/_**funnel\_id**_.json

### 请求类型

GET

### 请求头参数

请参考[认证](../../authenticate/)&gt;[公共请求参数](../../authenticate/head-parameter.md)获取。

### 参数说明与示例

{% tabs %}
{% tab title="请求参数" %}
| 路径参数 | 类型 | 是否必传 | 说明 |
| :--- | :--- | :--- | :--- |
| funnel\_id | string | 是 | 漏斗分析单图ID。 |
| project\_uid | string | 是 | 项目UID。 |

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x67E5;&#x8BE2;&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x4F20;</th>
      <th style="text-align:left">&#x8BF4;&#x660E;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">conversionWindow</td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">&#x8F6C;&#x5316;&#x5468;&#x671F;</td>
    </tr>
    <tr>
      <td style="text-align:left">startTime</td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">
        <p>&#x6570;&#x636E;&#x8D77;&#x59CB;&#x65F6;&#x95F4;&#xFF0C;unix&#x6BEB;&#x79D2;&#x65F6;&#x95F4;&#x9519;&#x3002;</p>
        <p>&#x9700;&#x4E0E;endTime&#x4E00;&#x8D77;&#x4F7F;&#x7528;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">endTime</td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">
        <p>&#x6570;&#x636E;&#x7ED3;&#x675F;&#x65F6;&#x95F4;&#xFF0C;unix&#x6BEB;&#x79D2;&#x65F6;&#x95F4;&#x6233;&#x3002;</p>
        <p>&#x9700;&#x4E0E;startTime&#x4E00;&#x8D77;&#x4F7F;&#x7528;&#x3002;</p>
      </td>
    </tr>
  </tbody>
</table>
{% endtab %}

{% tab title="响应示例" %}
200：OK

```text
{
"id":  "Funnel Uid",
"name":  "Funnel Name",
"conversionWindow":  1,
"startTime":  1571068800000,
"endTime":  1572278399999,
"interval":  86400000,
"meta":  [
    {"name":"目标用户","dimension":true},
    {"name":"时间","dimension":true},
    {"name":"总转化率","metric":true},
    {"name":"第一步人数","metric":true},
    {"name":"第一步转化率","metric":true},
    ...
    {"name":"最后一步人数","metric":true},
    {"name":"最后一步转化率","metric":true}
]
"data":  [
    [目标用户, 时间, 总转化率, 第一步人数, ... , 最后一步转化率],
    [目标用户, 时间, 总转化率, 第一步人数, ... , 最后一步转化率],
    ...
]
}
```
{% endtab %}
{% endtabs %}

