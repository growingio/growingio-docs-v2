# 导出原始数据

### URL

https://www.growingio.com/insights/_**ai**_/_**date**_.json

### 请求类型

GET

### 请求头参数

请参考[认证](../../authenticate/)&gt;[公共请求参数](../../authenticate/head-parameter.md)获取。

### 参数说明与示例

{% tabs %}
{% tab title="请求参数" %}
<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x8DEF;&#x5F84;&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x4F20;</th>
      <th style="text-align:left">&#x8BF4;&#x660E;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">ai</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x9879;&#x76EE;ID</td>
    </tr>
    <tr>
      <td style="text-align:left">date</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">
        <p>&#x6570;&#x636E;&#x65E5;&#x671F;</p>
        <p>&#x5929;&#x7EA7;&#x522B;&#x793A;&#x4F8B;&#xFF1A;20160520</p>
        <p>&#x5C0F;&#x65F6;&#x7EA7;&#x522B;&#x793A;&#x4F8B;&#xFF1A;20160502008</p>
        <p>&#x6709;&#x9ED8;&#x8BA4;&#x503C;&#x5417;&#xFF1F;&#xFF1F;&#xFF1F;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x67E5;&#x8BE2;&#x53C2;&#x6570;expire</td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">
        <p>&#x8FC7;&#x671F;&#x65F6;&#x95F4;&#xFF0C;&#x4EE5;&#x5206;&#x4E3A;&#x5355;&#x4F4D;</p>
        <p>&#x975E;&#x5FC5;&#x4F20;&#x7684;haul&#x9ED8;&#x8BA4;&#x503C;&#x662F;&#x591A;&#x5C11;
          5&#x5417; &#xFF1F;</p>
      </td>
    </tr>
  </tbody>
</table>
{% endtab %}

{% tab title="返回示例" %}
```text
{
  "status": "FINISHED",
  "downlinks": [
    "link1",
    "link2"
  ]
}
```

响应中的 status 字段，状态值有： 1. FINISHED 任务完成； 2. RUNNING 任务正在跑； 3. NOT\_EXISTS 任务不存在，可能是任务还没跑或者请求日期格式不对。

使用下载链接时，可以先检查 status 字段，为 FINISHED 时才拿 downlinks 进行下载。？？？status状态还没到finished时候，链接已经有了吗？？？
{% endtab %}
{% endtabs %}



























