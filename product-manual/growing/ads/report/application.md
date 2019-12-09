# 应用级数据

推广数据根据应用的不同分为：App应用推广数据、网页应用推广数据、微信小程序推广数据。

## App 应用推广数据

### 数据指标概念

* 激活：激活是指 App下载后首次联网打开 SDK 会上报一条该设备的激活数据，该指标可理解为 App 的下载安装量。
* 激活总量：通过 SDK 上报至 GrowingIO 的全部激活设备总量。
* 推广激活：通过监测链接监测到发生激活的设备。
* 推广新激活：推广激活设备的排重后数量，对同一设备在时间周期内（30天）反复激活仅记一次。

### 全局设定

![](https://docs.growingio.com/.gitbook/assets/-LGNxeGABUADKiTWTaEM-LeHja1phuKvd8Myv00g-LeHmONcAo6FRSGpEbJLimage.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x9879;</th>
      <th style="text-align:left">&#x8BF4;&#x660E;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x65F6;&#x95F4;</td>
      <td style="text-align:left">&#x53EF;&#x901A;&#x8FC7;&#x65F6;&#x95F4;&#x63A7;&#x4EF6;&#x8BBE;&#x5B9A;&#x5F53;&#x524D;&#x62A5;&#x8868;&#x6570;&#x636E;&#x7EDF;&#x8BA1;&#x65F6;&#x95F4;&#x6BB5;&#xFF0C;&#x65F6;&#x95F4;&#x8303;&#x56F4;&#x8BBE;&#x5B9A;&#x540E;&#x5C06;&#x5E94;&#x7528;&#x5728;&#x62A5;&#x8868;&#x5168;&#x5C40;&#x3002;&#xFF08;&#x4E0A;&#x56FE;&#x4F4D;&#x7F6E;
        1 &#x6240;&#x793A;&#xFF09;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x6DFB;&#x52A0;&#x4E1A;&#x52A1;&#x8F6C;&#x5316;&#x76EE;&#x6807;</td>
      <td
      style="text-align:left">&#x53EF;&#x4EE5;&#x6DFB;&#x52A0;&#x60A8;&#x5173;&#x6CE8;&#x7684;&#x4E1A;&#x52A1;&#x8F6C;&#x5316;&#x6307;&#x6807;&#xFF0C;&#x8BE5;&#x4E1A;&#x52A1;&#x6307;&#x6807;&#x5728;&#x4E0B;&#x65B9;&#x56FE;&#x8868;&#x4E2D;&#x5C06;&#x4F5C;&#x4E3A;&#x57FA;&#x672C;&#x7684;&#x5206;&#x6790;&#x6570;&#x636E;&#x6307;&#x6807;&#x3002;&#xFF08;&#x4E0A;&#x56FE;&#x4F4D;&#x7F6E;
        2 &#x6240;&#x793A; &#xFF09;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5168;&#x5C40;&#x6570;&#x636E;</td>
      <td style="text-align:left">
        <p>&#x5C55;&#x793A;&#x5F53;&#x524D;&#x79FB;&#x52A8;&#x7AEF;&#x5E7F;&#x544A;&#x6295;&#x653E;&#x73AF;&#x8282;&#x7684;&#x57FA;&#x672C;&#x76D1;&#x63A7;&#x6307;&#x6807;&#x6570;&#x636E;&#x3002;&#xFF08;&#x4E0A;&#x56FE;&#x4F4D;&#x7F6E;
          3 &#x6240;&#x793A; &#xFF09;</p>
        <p>&#x5468;&#x671F;&#x5BF9;&#x6BD4;&#xFF1A;&#x6839;&#x636E;&#x5F53;&#x524D;&#x9009;&#x62E9;&#x7684;&#x65F6;&#x6BB5;&#xFF0C;&#x8BA1;&#x7B97;&#x5468;&#x671F;&#x5BF9;&#x6BD4;&#xFF0C;&#x5F53;&#x524D;&#x4E3A;&#x5468;&#x5BF9;&#x6BD4;&#xFF0C;&#x5E76;&#x63D0;&#x4F9B;&#x8BF4;&#x660E;&#x672C;&#x5468;&#x671F;&#x4E0E;&#x4E0A;&#x5468;&#x671F;&#x65F6;&#x95F4;&#x8BA1;&#x7B97;&#x533A;&#x95F4;&#x3002;</p>
        <p>&#x5168;&#x5C40;&#x6570;&#x636E;&#x4E2D;&#x5404;&#x6307;&#x6807;&#x95F4;&#x6570;&#x636E;&#x65E0;&#x53D1;&#x751F;&#x5148;&#x540E;&#x987A;&#x5E8F;&#x903B;&#x8F91;&#x5173;&#x8054;&#xFF0C;&#x5404;&#x6307;&#x6807;&#x6570;&#x636E;&#x4E3A;&#x5355;&#x6307;&#x6807;&#x72EC;&#x7ACB;&#x7EDF;&#x8BA1;&#x7684;&#x52A0;&#x548C;&#x6570;&#x636E;&#x3002;</p>
      </td>
    </tr>
  </tbody>
</table>### 激活设备数据

展示当前 App 下的激活数据，以线图方式展示数据变化情况，结合右侧提供圆环图，可快速了解当前推广激活占整体激活的比例，以及推广新激活在推广激活中的占比分布，方便衡量活动推广效率及活动推广质量。

此图表支持数据导出，通过右上角下载按钮即可导出当前表格数据。

![](https://docs.growingio.com/.gitbook/assets/-LGNxeGABUADKiTWTaEM-LeHja1phuKvd8Myv00g-LeHmwXZttT00G8IfaSximage.png)

### 广告活动和渠道效果分析

以线图、柱图的方式展示当前选择的时段下，广告活动和广告渠道的数据情况，并在图表右侧提供简单洞察，可快速发现执行效果最优的广告活动以及广告渠道。

### 推广日报

推广日报可查看各链接级别的详细统计数据，上方数据图表中的数据逻辑与该推广日报统计逻辑一致。

支持按统计字段聚合展示数据，支持的字段包括：时间、推广活动、目标渠道、监测链接。

支持自定义表格列数据，通过自定义指标按钮可自定义需要展示的指标。

此报表支持数据导出，通过右上角下载按钮即可导出当前表格数据。

![](https://docs.growingio.com/.gitbook/assets/-LGNxeGABUADKiTWTaEM-LeHja1phuKvd8Myv00g-LeHny3MDD0Pw-GSoe_uimage.png)

### 推广详细

推广详细展示的数据会以监测链接在点击阶段收到数据进行归因，后续转化阶段数据皆会向本次点击归因，数据统计按照点击发生环节统计，此方式方便衡量各链接推广效率。

支持按字段聚合展示数据，支持的字段包括：时间、推广活动、目标渠道、监测链接。

支持自定义表格列数据，通过自定义指标按钮可自定义需要展示的指标。

此报表支持数据导出，通过右上角下载按钮即可导出当前表格数据。

![](https://docs.growingio.com/.gitbook/assets/-LGNxeGABUADKiTWTaEM-LeHja1phuKvd8Myv00g-LeHpB9Bj5mNyB5UsV0wimage.png)

### 异常数据报告

系统会针对广告投放运行一系列模型&规则识别数据的异常性，并提供相关数据报告。 1. 选中目标 App，进入“基础数据”中“异常数据报告”模块。 2. 可以根据业务诉求进行部分异常数据识别规则配置。 3. 可点击“自定义列指标”进行指标选择，可选择的列指标有：去重点击，激活，异常点击，异常激活。

![](https://docs.growingio.com/.gitbook/assets/-LGNxeGABUADKiTWTaEM-Lg2AUnk60Vr7H8CnSwJ-Lg2AXXNODclY_3UgtjQimage.png)

## 网页应用推广数据

### 数据指标概念

* 点击：GrowingIO 监测链接的点击数统计。
* 进入量：访问用户进入网站进行访问的数量。
* 访问用户量：访问用户的数量。
* 新访问用户量：过去 365 天内首次访问用户的数量。

### **全局设定**

![](https://docs.growingio.com/.gitbook/assets/-LGNxeGABUADKiTWTaEM-LeHgAxqElp3IcWMpkcp-LeHgZ2zvDAGpbCgAnyRE59BBEE78987.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>&#x9879;</b>
      </th>
      <th style="text-align:left">&#x8BF4;&#x660E;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x65F6;&#x95F4;</td>
      <td style="text-align:left">
        <p>&#x53EF;&#x901A;&#x8FC7;&#x65F6;&#x95F4;&#x63A7;&#x4EF6;&#x8BBE;&#x5B9A;&#x5F53;&#x524D;&#x62A5;&#x8868;&#x6570;&#x636E;&#x7EDF;&#x8BA1;&#x65F6;&#x95F4;&#x6BB5;&#xFF0C;&#x65F6;&#x95F4;&#x8303;&#x56F4;&#x8BBE;&#x5B9A;&#x540E;&#x5C06;&#x5E94;&#x7528;&#x5728;&#x62A5;&#x8868;&#x5168;&#x5C40;&#x3002;&#xFF08;&#x4E0A;&#x56FE;&#x4F4D;&#x7F6E;
          1 &#x6240;&#x793A;&#xFF09;</p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x4E1A;&#x52A1;&#x8F6C;&#x5316;&#x76EE;&#x6807;</td>
      <td style="text-align:left">&#x53EF;&#x4EE5;&#x6DFB;&#x52A0;&#x60A8;&#x5173;&#x6CE8;&#x7684;&#x4E1A;&#x52A1;&#x8F6C;&#x5316;&#x6307;&#x6807;&#xFF0C;&#x8BE5;&#x4E1A;&#x52A1;&#x6307;&#x6807;&#x5728;&#x4E0B;&#x65B9;&#x56FE;&#x8868;&#x4E2D;&#x5C06;&#x4F5C;&#x4E3A;&#x57FA;&#x672C;&#x7684;&#x5206;&#x6790;&#x6570;&#x636E;&#x6307;&#x6807;&#x3002;&#xFF08;&#x4E0A;&#x56FE;&#x4F4D;&#x7F6E;
        2 &#x6240;&#x793A; &#xFF09;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x5168;&#x5C40;&#x6570;&#x636E;</td>
      <td style="text-align:left">
        <p>&#x5C55;&#x793A;&#x5F53;&#x524D; Web &#x7AEF;&#x5E7F;&#x544A;&#x6295;&#x653E;&#x73AF;&#x8282;&#x7684;&#x57FA;&#x672C;&#x76D1;&#x63A7;&#x6307;&#x6807;&#x6570;&#x636E;&#x3002;&#xFF08;&#x4E0A;&#x56FE;&#x4F4D;&#x7F6E;
          3 &#x6240;&#x793A; &#xFF09;</p>
        <p>&#x5468;&#x671F;&#x5BF9;&#x6BD4;&#xFF1A;&#x6839;&#x636E;&#x5F53;&#x524D;&#x9009;&#x62E9;&#x7684;&#x65F6;&#x6BB5;&#xFF0C;&#x8BA1;&#x7B97;&#x5468;&#x671F;&#x5BF9;&#x6BD4;&#xFF0C;&#x5F53;&#x524D;&#x4E3A;&#x5468;&#x5BF9;&#x6BD4;&#xFF0C;&#x5E76;&#x63D0;&#x4F9B;&#x8BF4;&#x660E;&#x672C;&#x5468;&#x671F;&#x4E0E;&#x4E0A;&#x5468;&#x671F;&#x65F6;&#x95F4;&#x8BA1;&#x7B97;&#x533A;&#x95F4;&#x3002;</p>
        <p>&#x5168;&#x5C40;&#x6570;&#x636E;&#x4E2D;&#x5404;&#x6307;&#x6807;&#x95F4;&#x6570;&#x636E;&#x65E0;&#x53D1;&#x751F;&#x5148;&#x540E;&#x987A;&#x5E8F;&#x903B;&#x8F91;&#x5173;&#x8054;&#xFF0C;&#x5404;&#x6307;&#x6807;&#x6570;&#x636E;&#x4E3A;&#x5355;&#x6307;&#x6807;&#x72EC;&#x7ACB;&#x7EDF;&#x8BA1;&#x7684;&#x52A0;&#x548C;&#x6570;&#x636E;&#x3002;</p>
      </td>
    </tr>
  </tbody>
</table>### 广告活动和渠道效果分析

以线图、柱图的方式展示当前选择的时段下，广告活动和广告渠道的数据情况，并在图表右侧提供简单洞察，可快速发现执行效果最优的广告活动以及广告渠道。

### 活动效果对比

| 项 | 说明 |
| :--- | :--- |
| 访问用户量/点击量 | 在活动效果对比中，可直接结合用户行为数据，对比不同活动间的转化效果，使用折线图来比较广告活动访问用户量、广告活动点击数据，分析对比两个活动间的同期效果。 |
| 转化漏斗 | 以转化漏斗形式展示从广告活动点击到目标页访问（落地页），再到设定的转化目标，各环节的转化情况，对比不同活动间的转化效率。 |
| 访问人数渠道贡献 | 展示在到达目标页面的访问人数中，不同渠道的访问人数占比，对比各渠道的投放效果。 |

### 报表详情数据

**推广详情**

推广详细可查看各链接级别的详细统计数据，上方数据图表中展示的数据依照该推广日报。

支持按字段聚合展示数据，支持的字段包括：时间、推广活动、目标渠道、监测链接**。**

此报表支持数据导出，通过右上角下载按钮即可导出当前表格数据。

![](https://docs.growingio.com/.gitbook/assets/-LGNxeGABUADKiTWTaEM-LeHgluGjm1y4gHUszxj-LeHh0rbhQ-BNzrWQ-xTimage.png)

#### ​ <a id="22"></a>

