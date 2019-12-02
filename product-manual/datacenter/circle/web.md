# Web端数据定义（Web圈选）

## 圈选准备

GrowingIO 全量采集用户行为数据，你可以通过「圈选」来定义元素和页面，作为数据分析的基础指标。

在没有定义过的情况下，GrowingIO 保留和回溯元素过去 7 天的点击量，页面过去 7 天的浏览量。

{% hint style="info" %}
Hashtag使用说明

如果您的Web页面URL使用了Hashtag，请在加载SDK进行预先配置，请参考[Web JS SDK](../../../developer-manual/sdkintegrated/web-js-sdk/)。
{% endhint %}

{% hint style="success" %}
URL解读

URL**示意：**www.xxx.com**/**12345/678/123**?**id=1&ig=2

**拆分：**域名**/**路径**?**查询条件

**即** www.xxx.com **为域名，**/12345/678/123 **为路径，**?id=1&ig=2 **为查询条件**
{% endhint %}

![](https://docs.growingio.com/.gitbook/assets/9412f46a-d87c-41ef-9ee6-9e6e408f4c6a-12626-00000bcf696b73c5_tmp.jpg)

## 圈选操作 <a id="1-kai-shi-quan-xuan"></a>

在顶部导航栏选择“**数据中心 &gt; 无埋点事件定义（圈选） &gt; 您的Web应用”**，进入Web圈选模式。

{% hint style="success" %}
Web圈选模式分为浏览和圈选两个模式

浏览模式：在浏览模式下选择您要圈选页面或元素所在页面。

圈选模式：在选定页面后进入圈选模式，定义页面中的元素。
{% endhint %}

{% tabs %}
{% tab title="定义页面" %}
1、在浏览模式下进入要定义的页面，单击圈选模式下的**定义页面**按钮，进入**定义页面**界面**。**

![](../../../.gitbook/assets/image%20%2855%29.png)

左侧选择区：显示与当前页面URL相同的页面（以【当前页】为标识），或包含当前页面的页面。如果页面已经被定义过，可以直接使用。

右侧编辑区：按照页面结构，我们把一个完成的URL拆解成了域名、路径和查询条件（如有则显示）。

路径：定义页面时会自带路径，打开路径表示定义的是当前路径页面，关闭路径后表示定义的是符合域名条件的所有页面。

查询：当页面有查询条件时会自带查询条件，打开查询表示定义的是符合查询条件的所有页面，关闭查询不对查询条件进行定义。

{% hint style="info" %}
**使用查询条件说明**

打开查询条件的页面数据不支持回溯，将从页面定义的时候开始统计数据。
{% endhint %}

{% hint style="success" %}
**定义一组页面**

支持在路径中使用 \* 作为通配符，达到定义一组类似页面的功能。

例如GrowingIO 博客文章内容的地址都是这样的 

* **https://blog.growingio.com/posts/123456**
* **https://blog.growingio.com/posts/14562**
* **https://blog.growingio.com/posts/1264**......

那么我们在路径中输入 /posts/\* 就会圈选出所有的博客单篇文章的页面。
{% endhint %}

2、配置参数定义参数后单击**保存**，完成对此页面的定义。

> 对于已被定义过的页面您在修改参数后进行更新或另存为操作。
{% endtab %}

{% tab title="定义元素" %}
1、 在浏览模式下进入要定义元素所在的页面，单击**圈选**，进入元素圈选模式**。**

2、 单击待定义的元素，弹出定义元素界面。

{% hint style="info" %}
当需要定义需要鼠标悬浮等交互行为才能显示的元素时，您可以按住shift键，待元素出现后进行圈选定义。
{% endhint %}

![](../../../.gitbook/assets/image%20%284%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x8BF4;&#x660E;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x6240;&#x5C5E;&#x9875;&#x9762;</td>
      <td style="text-align:left">&#x786E;&#x8BA4;&#x5143;&#x7D20;&#x6240;&#x5728;&#x7684;&#x9875;&#x9762;&#x662F;&#x4EC0;&#x4E48;&#x3002;&#x5982;&#x679C;&#x8FD9;&#x4E2A;&#x5143;&#x7D20;&#x51FA;&#x73B0;&#x5728;&#x591A;&#x4E2A;&#x9875;&#x9762;&#x540C;&#x6837;&#x7684;&#x4F4D;&#x7F6E;&#xFF0C;&#x60F3;&#x8981;&#x7EDF;&#x8BA1;&#x6240;&#x6709;&#x7684;&#x6570;&#x636E;&#xFF0C;&#x53EF;&#x4EE5;&#x901A;&#x8FC7;&#x201D;&#x5B9A;&#x4E49;&#x9875;&#x9762;&#x201C;&#xFF0C;&#x5148;&#x5B9A;&#x4E49;&#x5143;&#x7D20;&#x6240;&#x5728;&#x7684;&#x9875;&#x9762;&#x7EC4;&#xFF0C;&#x5728;&#x5728;&#x8FD9;&#x91CC;&#x9009;&#x62E9;&#x8BE5;&#x9875;&#x9762;&#x7EC4;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x9650;&#x5B9A;&#x6761;&#x4EF6;</td>
      <td style="text-align:left">
        <p>&#x8BBE;&#x7F6E;&#x5143;&#x7D20;&#x5F53;&#x524D;&#x7684;&#x6587;&#x672C;&#x3001;&#x987A;&#x5E8F;&#x3001;&#x8F6C;&#x8DF3;&#x94FE;&#x63A5;&#x7B49;&#x9650;&#x5B9A;&#x6761;&#x4EF6;&#xFF0C;&#x786E;&#x5B9A;&#x5143;&#x7D20;&#x7EDF;&#x8BA1;&#x7684;&#x89C4;&#x5219;&#x3002;</p>
        <p>&#x5185;&#x5BB9;&#xFF1A;</p>
        <p>&#x987A;&#x5E8F;&#x4F4D;&#xFF1A;</p>
        <p>&#x8F6C;&#x8DF3;&#x94FE;&#x63A5;&#xFF1A;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x52A8;&#x6001;&#x5C55;&#x793A;&#x533A;</td>
      <td style="text-align:left">&#x901A;&#x8FC7;&#x52A8;&#x6001;&#x5C55;&#x793A;&#x533A;&#x786E;&#x8BA4;&#x662F;&#x4E0D;&#x662F;&#x81EA;&#x5DF1;&#x60F3;&#x8981;&#x5B9A;&#x4E49;&#x7684;&#x5143;&#x7D20;&#x548C;&#x89C4;&#x5219;&#x3002;</td>
    </tr>
  </tbody>
</table>3、配置完成后单击**保存**，完成此元素的定义。

> 对于已被定义过的元素您在修改参数后进行另存为操作。

{% hint style="info" %}
**高亮显示说明**

圈选导航栏上显示默认开启了**「高亮已定义元素」**，您可以看到哪些元素被定义过。

高亮模式下，粉色实线代表已经被圈选的元素，粉色虚线代表已经被圈选的同类元素，点击元素后可以看到最近一次被定义的规则。

单击**显示**，可选择关闭高亮显示。
{% endhint %}
{% endtab %}

{% tab title="将查询条件设置为页面级变量" %}
> SDK版本支持：&gt;=2.x

以https://www.growingio.com/projects/1/homepage/overview?platform=ios&channel=banner为例，“?”后面的部分我们通常叫做查询条件（Query），在这个 URL 中标记了这个页面是在哪个平台（platform）打开的，以及通过哪个渠道（channel）访问的等重要信息，不同的公司有不同的应用，这种应用非常常见，那么，我们如何把这些重要的信息利用起来呢？

现在不需要埋点和开发，可以直接将这些查询条件设置成页面级变量，即维度；不仅如此，相比与埋点信息的延时发送，GrowingIO 将页面与查询条件中的信息同时发送、采集和计算，没时差，再也不会有那么多的空值了。

#### 操作步骤

1、 在圈选模式下选择带有查询条件的页面，单击页面上方的**定义页面级变量。**

2、 选择需要定义的查询条件，为查询条件（标识符）命名后单击确定。

![](../../../.gitbook/assets/image%20%28112%29.png)

{% hint style="info" %}
页面级变量说明

全局生效，一旦设置，全站采集，对域名下的所有加载了SDK的页面生效。

埋点优先，埋点页面的数据不受任何影响，只在没有埋点或延时导致埋点数据没有发出来时，会取”标识符“相同的查询条件对应的值。
{% endhint %}

### **设置查询条件为页面级变量的案例详解** <a id="2-an-li-xiang-jie"></a>

如果你之前进行了埋点，那么这个功能上线后会发生什么变化呢？

电商客户 S 为了分析商品的售卖情况，在详情页进行了埋点，将每个商品的编号、商品名称等设置成了页面级变量，已经实施后上线了，其中商品编号标识符为 id，是从内容中取值的。接下来，用户用这个页面级变量来拆分商品详情页，进行分析。

假设商品详情页的 URL 是这样的 www.s.com/pro?id=342817&city=bj ，我们可以看到查询条件中的 id 就是这个商品的商品编号， **当这个功能上线后，由于「商品编号标识符： id」与「查询条件中的：id 」是一样的，我们会从打点设置的规则和 URL 中的查询条件中同时取 id 的值，**有如下几种情况：

> 表格第四列「埋点取的值」 - 客户打点时的规则是从「内容」中取值；
>
> 表格第五列「URL 取的值」 - 这个功能上线后我们从 URL 中取到对应的 key 的值。

{% hint style="success" %}
对于下面表格内容的总结

1.只要埋点取到了值，就取埋点的值。（表格中的第 1 个和第 2 个情况）

2.如果一个页面上，没有埋点的值，不管是因为这个页面没有埋点，还是因为发送时间导致没有发送出来，会取查询条件中取到的值。（表格中的第 3 个和第 4 个情况）
{% endhint %}

<table>
  <thead>
    <tr>
      <th style="text-align:left">#</th>
      <th style="text-align:left">&#x200B;</th>
      <th style="text-align:left">&#x53D8;&#x5316;</th>
      <th style="text-align:left">&#x57CB;&#x70B9;&#x53D6;&#x7684;&#x503C;</th>
      <th style="text-align:left">URL &#x53D6;&#x7684;&#x503C;</th>
      <th style="text-align:left">&#x4E4B;&#x524D;</th>
      <th style="text-align:left">&#x4E4B;&#x540E;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x7B2C; 1 &#x4E2A;&#x60C5;&#x51B5;</td>
      <td style="text-align:left">
        <p><b>&#x5546;&#x54C1;&#x8BE6;&#x60C5;&#x9875;1</b>
        </p>
        <p>&#x5546;&#x54C1;&#x9875;&#x5185;&#x5BB9;&#x4E2D;&#x7684;&#x503C; 342817</p>
        <p>www.s.com/pro?id=342817&amp;city=bj</p>
      </td>
      <td style="text-align:left">&#x65E0;&#x53D8;&#x5316;</td>
      <td style="text-align:left"><b>342817</b>
      </td>
      <td style="text-align:left">342817</td>
      <td style="text-align:left">342817</td>
      <td style="text-align:left"><b>342817</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x7B2C; 2 &#x4E2A;&#x60C5;&#x51B5;</td>
      <td style="text-align:left">
        <p><b>&#x5546;&#x54C1;&#x8BE6;&#x60C5;&#x9875;1</b>
        </p>
        <p>&#x5546;&#x54C1;&#x9875;&#x5185;&#x5BB9;&#x4E2D;&#x7684;&#x503C; ac487</p>
        <p>www.s.com/pro?id=342816&amp;city=bj</p>
      </td>
      <td style="text-align:left">&#x65E0;&#x53D8;&#x5316;</td>
      <td style="text-align:left"><b>ac487</b>
      </td>
      <td style="text-align:left">342816</td>
      <td style="text-align:left">ac487</td>
      <td style="text-align:left"><b>ac487</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x7B2C; 3 &#x4E2A;&#x60C5;&#x51B5;</td>
      <td style="text-align:left">
        <p><b>&#x5546;&#x54C1;&#x8BE6;&#x60C5;&#x9875;2</b>
        </p>
        <p>&#x5546;&#x54C1;&#x9875;&#x5185;&#x5BB9;&#x4E2D;&#x7684;&#x503C; 342815
          &#xFF0C;&#x4F46;&#x662F;&#x56E0;&#x4E3A;&#x65F6;&#x95F4;&#x7684;&#x7F18;&#x6545;&#xFF0C;&#x6CA1;&#x6709;&#x53D1;&#x51FA;&#x6765;&#x8FD9;&#x4E2A;&#x503C;</p>
        <p>www.s.com/pro?id=342815&amp;city=bj</p>
      </td>
      <td style="text-align:left">&#x8865;&#x4E86;&#x503C;</td>
      <td style="text-align:left">NA</td>
      <td style="text-align:left"><b>342815</b>
      </td>
      <td style="text-align:left">NA</td>
      <td style="text-align:left"><b>342815</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x7B2C; 4 &#x4E2A;&#x60C5;&#x51B5;</td>
      <td style="text-align:left">
        <p><b>&#x5546;&#x54C1;&#x8BA2;&#x5355;&#x9875;1</b>
        </p>
        <p>&#x8BA2;&#x5355;&#x9875;&#x6CA1;&#x6709;&#x6253;&#x70B9;&#xFF0C;&#x6240;&#x4EE5;&#x8FD9;&#x91CC;&#x6CA1;&#x6709;&#x6253;&#x70B9;&#x7684;&#x503C;</p>
        <p>www.s.com/orderform?id=53462&amp;city=bj</p>
      </td>
      <td style="text-align:left">&#x8865;&#x4E86;&#x503C;</td>
      <td style="text-align:left">NA</td>
      <td style="text-align:left">NA</td>
      <td style="text-align:left">
        <p><b>53462</b>
        </p>
        <p>&#x26A0;&#xFE0F;&#xFF1A;&#x672C;&#x6765;&#x7528;&#x6237;&#x6CA1;&#x6709;&#x6253;&#x70B9;&#xFF0C;&#x62FF;&#x4E0D;&#x5230;&#x6570;&#x636E;&#xFF0C;&#x73B0;&#x5728;&#x6709;&#x4E86;&#x8BA2;&#x5355;&#x7F16;&#x53F7;&#x4E1A;&#x52A1;&#x610F;&#x4E49;&#x7684;&#x6570;&#x636E;&#x3002;&#x8FD9;&#x4E2A;&#x4E1A;&#x52A1;&#x610F;&#x4E49;&#x4E0E;&#x524D;&#x9762;&#x7684;&#x5546;&#x54C1;&#x7F16;&#x53F7;&#x4E0D;&#x540C;&#x3002;</p>
      </td>
      <td style="text-align:left"><b>53462</b>
      </td>
    </tr>
  </tbody>
</table>### 其他特殊情况 <a id="3-qi-ta-te-shu-qing-kuang"></a>

* 取到的查询条件是b=时，则传 N/A，与现在一致；
* 查询条件里有 b=1&b=2 ，取 b 的值为 2 ；
* URL 中存在 ?a=1\#?b=2 ，第一个?是查询条件，即查询条件为a=1，第一个\#是hash，即hash（路径中的一部分）为?b=2；
* 解析移动端的数据；
{% endtab %}
{% endtabs %}

{% hint style="success" %}
查看最近更新

单击圈选页面右上角的最近更新，查看刚刚定义的元素。
{% endhint %}

## 定义页面案例

### **基础步骤 \| 监控首页和全站的流量情况**

#### **1.定义首页：**

对于每个公司来说，首页都是比较重要的页面，通常会分析首页的流量从哪里来，以及首页的转化能力。首先，我要定义 GrowingIO 的首页。

第一步：在「圈选导航栏」中输入 url ，回车或点击跳转；

第二步：点击「定义页面」；

第三步：确认现在定义的页面 url 是否正确，修改「页面的名称」，保存。

![](https://docs.growingio.com/.gitbook/assets/20_40_02__04_25_2018.jpg)

定义完页面后，可以去「事件分析」中选择这个指标，就可以看到这个页面的基本数据情况了。

可以在「表格」中使用「访问来源」的维度来查看这个页面的流量都是从哪里来，也可以在案例2中学习到转化率的分析。

#### **2.定义全站页面组：**

如果你想看到全站的总体流量情况，可以定义全站页面组。

在上面的第二步，点击「页面定义」后：

第一步：关闭「路径」开关；

第二步：确认现在定义的页面是否是域名下的所有页面；

![](https://docs.growingio.com/.gitbook/assets/21_04_22__04_25_2018.jpg)

### **案例一：注册转化率分析（定义每一个转化节点）**

注册流是很常见的转化流程了，注册数往往关乎核心的业务指标，因此，通常我们会有这样的分析需求。

首先，我们需要清楚自己的注册流程是什么样的，比如是否分页，每一个按钮点击后是否一定会触达跳转，在这个转化流程中的关键节点有哪些。

接下来，我们来看一个注册流程：

![](https://docs.growingio.com/.gitbook/assets/image003.png)

这是一个分页的注册流程，用户填写完上一页的内容才能进入到下一页，因此我可以将这三个页面作为漏斗的三个步骤，按照案例1的方式定义每一个页面。

然后，在漏斗分析中进行分析：

![](https://docs.growingio.com/.gitbook/assets/image005.png)

### **案例二：一组页面的分析（定义一组有相关业务意义的页面）**

很多网站的页面都是有规律的，层级结构清晰：

GrowingIO 解决方案首页 **https://www.growingio.com/solution/**​

GrowingIO 在线旅游解决方案落地页 **https://www.growingio.com/solution/online-travel**

GrowingIO 互联网金融解决方案落地页 **https://www.growingio.com**​**/solution/internet-finance**

我们发现所有的解决方案落地页都是 **https://www.growingio.com/solution/xxx** ，那么如果我想统计所有解决方案页的页面情况，就可以通过通配符「\*」来定义一组页面 **https://www.growingio.com/solution/\***，即：​

![](https://docs.growingio.com/.gitbook/assets/20_59_35__04_25_2018.jpg)

### **案例三：特殊页面定义——页面 url 中带有 「?」**

如果你发现你的页面 url 中带有「?」，除了用于监测广告投放的 utm 之外，需要在定义页面时手动打开「查询条件」的开关，这种情况是不支持回溯数据的，将从你定义页面的时候开始统计数据：

![](https://docs.growingio.com/.gitbook/assets/21_17_01__04_25_2018.jpg)

## **定义元素案例**

### **基本步骤 \| 监控重要的按钮数据（定义元素）**

注册按钮在首页的点击量是一个重要的数据，因此，我们需要定义这个元素。

首先，在「圈选」模式下点击这个按钮：

第一步：确认元素所在页面是否正确，默认的是「当前页面」；

第二步：根据下图中第二个蓝色框中的文字，确认统计规则是否符合需求；

第三步：填写一个容易理解的名称，然后就可以保存了。

![](https://docs.growingio.com/.gitbook/assets/21_20_14__04_25_2018.jpg)

接下来，可以在「事件分析」等分析工具中使用。

### **案例一：分析一个商品位、测试按钮等（定义一个位置）**

我们在圈选时只能看到一种元素，但是可能用户看到的网站内容不一样，元素的内容也不一样，因此，当我们在定义一个元素时，要思考我们想要统计的是「现在这个位置的按钮点击情况」还是「这个位置上这个内容的按钮的点击情况」。常见于商品位、AB测试等使用场景。

在下图中，有一部分用户看到的按钮是「立即注册」，还有一部分用户看到的按钮是「免费试用」，因此，如果我想定义这个按钮的点击情况，不管是什么内容，那么就只「限定顺序」，不限定其他条件：​

![](https://docs.growingio.com/.gitbook/assets/21_32_36__04_25_2018%20%281%29.jpg)

如果想看这个位置上不同内容的点击情况，可以在「事件分析」中，选择「柱图」，用「元素内容」作为维度，来进行分析。

### **案例二：导航栏分析（定义一个跨页面的元素）**

如果想要分析导航栏的点击情况，我们就会发现这是一类特殊的元素，因为他们出现在网站的多个页面中。

因此，在定义这类元素时，要注意选择全站页面组，如果没有定义全站页面组，需要先去「定义页面」，详见「定义页面部分」的「基本步骤」。

![](https://docs.growingio.com/.gitbook/assets/21_29_04__04_25_2018.jpg)

### **案例三：比较一些长得差不多的元素（定义一组元素）**

当我们想要定义一组列表，或者一组元素时，会发现他们通常结构很像，圈选提供了一种便捷的方式，通过定义「同类元素」的方式来定义一组元素。选中这样的元素后，依然是先确认它的所属页面是否正确，然后「不限定任何限定条件」，这时可以注意第二个蓝框中的话：现在定义的是所属页面中，所有同类元素的数据之和。我们已经将这组同类元素用虚线框标记出来。这时，你就成功定义了这个元素所在的列表。

![](https://docs.growingio.com/.gitbook/assets/21_32_36__04_25_2018.jpg)

然后在「事件分析」中使用「元素内容」的维度进行分析。

## 插件圈选

GrowingIO 提供支持 eb 圈选的 Chrome 扩展程序。

**使用场景**

* window.name、window.top等被复写，导致圈选不了；
* 客户网站 block了外站加载 iframe，需要客户把我们加入白名单；
* https/http 切换问题；
* 客户网站的实现方式是新开一个tab显示新页面，现在会跳出 GIO；
* 客户的header里面设置了Allow-orign 为他们自己的网站 导致没法在我们的官网里面被圈选。

**插件安装**

> Chrome网上应用店一键安装（自动更新）：[https://chrome.google.com/webstore/detail/growingio-web%E5%9C%88%E9%80%89/iapmppbkobkiijkhndbnkncfaklmbhck](https://chrome.google.com/webstore/detail/growingio-web%E5%9C%88%E9%80%89/iapmppbkobkiijkhndbnkncfaklmbhck?authuser=3)​
>
> 插件（最新版）手动下载地址： [https://s.growingio.com/5EoKZl](https://s.growingio.com/5EoKZl)，请参考[手动安装插件方法](https://s.growingio.com/2Z4mBB)。

**圈选步骤**

1. **圈**选插件安装成功后，**直接在 Chrome 浏览器中打开待圈选网站**。
2. 单机插件图标登录你的账号。

![](https://docs.growingio.com/.gitbook/assets/-LGNxeGABUADKiTWTaEM-LrqhnRPBooFdHnT0FSY-LrqisorSxLz_gaBjKtcimage.png)

3. 将插件模式切换到圈选模式，就可以开始圈选了，插件圈选方式与页面圈选功能相同。

![](https://docs.growingio.com/.gitbook/assets/-LGNxeGABUADKiTWTaEM-LrqhnRPBooFdHnT0FSY-Lrqk4QSF2CnHLdo5gu6image.png)

## 常见问题 <a id="2-chang-jian-wen-ti-faq"></a>

### **1. 如何定义「一组相似元素之和」？** <a id="21-ru-he-ding-yi-yi-zu-xiang-si-yuan-su-zhi-he"></a>

如果该元素有同类元素，不限定所有的限定条件，即是统计一组同类元素之和的数据。

### **2. 对于已定义过的元素，更改定义规则后，应该如何保存？** <a id="22-dui-yu-yi-ding-yi-guo-de-yuan-su-geng-gai-ding-yi-gui-ze-hou-ying-gai-ru-he-bao-cun"></a>

更改新的规则后，如果原有数据仍然想继续统计，请选择“另存为”来定义新的规则。

### **3. 如何进行文本「内容」的模糊匹配？** <a id="23-ru-he-jin-hang-wen-ben-nei-rong-de-mo-hu-pi-pei"></a>

「限定内容」的情况下，将鼠标移动到「内容」的右边，可以看到一个小铅笔，点击小铅笔后，便打开了文本和模式编辑弹窗。默认为精准匹配，即「限定内容为xxx」，若改成模糊匹配，则意义是「限定内容包含xxx」。 保存元素规则后，将按照新的规则进行统计，如果原有数据仍然想继续统计，请选择「另存为」。

![](https://docs.growingio.com/.gitbook/assets/223435.jpg)

### **4. 月21日迭代后，新旧版本规则对应关系** <a id="24-3-yue-21-ri-die-dai-hou-xin-jiu-ban-ben-gui-ze-dui-ying-guan-xi"></a>

![](https://docs.growingio.com/.gitbook/assets/ping-mu-kuai-zhao-20180319-shang-wu-11.24.51.png)

### 5. 不能圈选的可能原因以及对应方法（web）

#### **不能圈选的原因**

不能圈选的原因包含了，但不仅限于：

* 元素包含属性：data-growing-ignore， 因此不可以被圈选。如果需要圈选该元素，请去除该属性。
* 密码框不支持被圈选。
* 元素已经被圈选，因此不能被重复圈选。
* 元素是叶子节点，无文本内容，且元素的占屏幕面积超过 50% ，因此不能被圈选。如果需要圈选该元素，请添加 data-growing-circle 属性。
*  元素所在的 Dom 嵌套层数过多，不在倒数后两层；或者层数符合但是没有实际内容，因此不能被圈选。

#### **data-growing-circle 属性的使用帮助：**

元素是叶子节点，无文本内容，且元素的占屏幕面积超过 50% ，因此不能被圈选。如果需要圈选该元素，请添加 data-growing-circle 属性。例如 ：

```text
 <div id= "d1" style="border: 1px solid black; width: 80%; height: 80%"></div>
```

本来不可以圈选。在添加 data-growing-circle 属性后可以圈选：

```text
<div  id= "d1" style="border: 1px solid black; width: 80%; height: 80%" data-growing-circle></div>
```

### **6. 如果我的页面改版，现在标记的指标是不是需要重新定义？**

改版后，变化的元素需要重新圈选。

### **7. 什么时候选择手动圈选，什么时候选择自动圈选？**

使用自动模式可以很方便快捷地圈选某些元素。但是有些时候由于页面框架的实现方式，自动圈选会圈选相似的模块进来，从而造成数据误差，所以必要时可以切换手动圈选来解决问题。

### **8. H5 怎么圈选？**

GrowingIO 可以统计原生应用中的 H5 页面和 H5 做成的应用。

* 原生应用中的 H5 页面，以及嵌在应用中的 H5，请参考 App端数据定义。 🍎 链接、
* 用 H5 做的应用请参考 Web端数据定义。 🍎 

### **9. 为什么圈选的元素只有点击量，没有浏览量？**

1. 如果被圈选元素是 a, button, input，img，并且在倒数两层以下，只统计点击量，不统计浏览量。
2. 如果用户使用的是 IE8 及以下的 IE 浏览器版本，无法统计浏览量 ，只统计点击量。

### **10. 为什么圈选的元素只有浏览量，没有点击量？**

1. 可能真的是没有点击量。
2. 可能选中的是纯文本等没有带超链接可点击的元素。

### **11. 当页面带查询条件的时候，开关查询条件，数据为什么没有变化？**

当圈选元素所在的页面带查询条件的时候，此时圈选框内展示的数据是不带查询条件的数据。保存带查询条件指标后，指标不会回溯数据，会从保存后开始统计数据。

### **12. Web 圈选时候页面加载不完全？错位？**

部分浏览器会有兼容性问题，推荐使用 Chrome 浏览器。

### **13. Web 端已经装了 SDK，现在不能进行圈选。**

1. 有可能是工程师没有成功加载 JS；
2. 可能是该网站禁止了 iframe 的加载，请联系工程师修改配置；
3. 可能是工程师加载 js 代码时的项目 ID 填写有误（项目 ID 没有空格）；
4. 有可能复写 window 对象：可视化圈选时候，必须要保证您的网站与 GrowingIO 平台之间的通信。如果 window.top, window.parent, window.name, window.location 被复写，将导致无法圈选。

如果出于某些原因你不能改变 iframe 或 window 相关设置，建议适应插件圈选 🍎 。

### **14. 能否在 iframe 中进行圈选？**

如果 iFrame 中的内容集成了 GrowingIO 的代码就可以圈选，否则无法圈选。 GrowingIO 是使用 iframe 来加载目标网页进行可视化定义的。如果目标网站禁止了 iframe 加载，就无法正常定义标签，当点击某个按钮的时候，页面无法发生跳转且命令行显示：

```text
Refused to display '**' in a frame because it set 'X-Frame-Options' to 'SAMEORIGIN'.
```

此时只允许同个顶级域名加载，所以需要设置http响应头允许 iframe 加载。

如果你的网站使用https协议，需向响应头添加配置

```text
Content-Security-Policy: frame-ancestors 'self' https://www.growingio.com
X-Frame-Options: Allow-From https://www.growingio.com
```

如果你的网站使用http协议，需向响应头添加配置

```text
Content-Security-Policy: frame-ancestors 'self' http://www.growingio.com
X-Frame-Options: Allow-From http://www.growingio.com
```

由于 Chrome 浏览器已经不再支持 X-Frame-Options 配置项，如果你只需在 Chrome 浏览器中进行圈选，建议通过浏览器检查后，只给 Chrome 请求的响应头添加配置

```text
Content-Security-Policy: frame-ancestors 'self' http://www.growingio.com https://www.growingio.com
```

### **15. 在 web 圈选的时候，为什么有时候会一下圈出一组同类元素，有办法区分开么？**

GrowingIO 根据您网站 HTML 结构识别和定义页面上的元素。有的时候网站上的 HTML 标签写法完全相同，呈现在页面上的几个同类元素，可能 HTML 代码完全相同。此时 GrowingIO 采集、圈选数据时无法区分开。我们通过 HTML 标签的 id 和 class 来区分元素，这种情况下您可以在需要区分的标签 class 中添加一些字符串用于区分。

**仍有疑问？请参考**[**常见问题－圈选部分**](https://docs.growingio.com/docs/faq/faq-circle)

