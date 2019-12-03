---
description: >-
  GrowingIO除了先进的数据分析理念和技术外，还从硅谷带来了对于数据安全与数据隐私极为重视的态度，我们将在每一个环节保证您的数据安全以及保护用户数据隐私。
---

# 数据安全

> SDK内容：

GrowingIO使用SSL对数据传输进行加密。

在基于网络的计算环境中，数据和应用的安全性至关重要。使用 AWS 公有云，对数据进行隔离处理，对数据的收集、处理以及存储机制进行安全审查，保障客户的数据安全。

> 常见问题内容：

#### 加密传输

数据全程使用超文本传输安全协议 \(https\) 进行传输，利用 SSL/TLS 加密数据包，能有效防护窃听与中间人攻击，最大程度地保护您数据传输的安全性。

#### 隔离保存 <a id="2&#x9694;&#x79BB;&#x4FDD;&#x5B58;"></a>

传输过来的数据会储存在云服务上，我们采用的是全球最大的云服务商 AWS，并集成了 AWS 的安全机制，在 GrowingIO 内部也拥有一套完整的安全机制和权限管理，并且生产和开发环境完全隔离。

> SDK内容：

### 员工访问数据说明 <a id="3"></a>

* 客户所有帐号数据都是机密，并受合同条款的约束。
* 未经客户明确许可，客户服务代表和技术支持人员不得访问客户级数据。
* 访问客户数据时，员工的活动范围仅限于履行工作职责所需的数据。
* 员工不得使用非 GrowingIO 所有或未经 GrowingIO 批准的网络设备访问数据。
* GrowingIO员工需要履行严格的合同保密义务，如果其未能履行这些义务，就可能会被追究法律责任或被终止其与GrowingIO的合同关系。

> 常见问题内容

#### 严格控制内部权限 <a id="3&#x4E25;&#x683C;&#x63A7;&#x5236;&#x5185;&#x90E8;&#x6743;&#x9650;"></a>

GrowingIO 的客户服务人员无权访问客户数据，除非客户直接授权客服登录。同时，您的管理账户里面都有日志记录，详细记录了谁对您的账户进行了操作，其中客户服务或者任何有权限的人的操作都有日志您可以查询。

GrowingIO 提供的是数据分析的产品，方法论和最佳实践，不做未经客户授权的任何数据交易相关的业务。

### 4.符合欧盟《一般数据保护条例》 \(GDPR\) <a id="4"></a>

2018年5月21日起，GrowingIO在Web、Android和iOS SDK中提供了以下的API供开发者调用满足客户网站或移动应用符合欧盟区的《一般数据保护条例》\(GDPR\)。

* GrowingIO SDK提供默认是否开启数据采集的配置项
* GrowingIO SDK提供关闭或开启全局数据采集的接口，开发者可在APP中任何场景时调用该接口
* GrowingIO SDK提供获取该设备的设备ID接口，开发者可配合数据侧提供的接口删除或导出该设备的行为数据

{% tabs %}
{% tab title="Android" %}
* 全局配置项

```java
.disableDataCollect() 
```

* 关闭或开启全局数据采集

```java
// 不采集数据 
GrowingIO.getInstance().disableDataCollect(); 
// 收集数据 
GrowingIO.getInstance().enableDataCollect();
```

* 获取访问用户ID

```java
GrowingIO.getInstance().getVisitUserId(); 
```

* 样例

```java
GrowingIO.startWithConfiguration(this, new Configuration() 
.disableDataCollect() // 开启GDPR， 不采集数据。 默认采集 
.useID() 
.trackAllFragments()); 
// 不采集数据 
GrowingIO.getInstance().disableDataCollect(); 
// 收集数据 
GrowingIO.getInstance().enableDataCollect(); 
// 获取访问用户ID 
GrowingIO.getInstance().getVisitUserId(); 
```
{% endtab %}

{% tab title="iOS" %}
* 全局配置项（无）
* 关闭或开启全局数据采集

```objectivec
disableDataCollect 
enableDataCollect 
```

* 获取访问用户ID

```objectivec
getVisitUserId 
```

* 样例

```objectivec
// 开启GDPR 
[Growing disableDataCollect]; 
// 关闭GDPR 
[Growing enableDataCollect]; 
// 获取设备ID 
NSString *viId = [Growing getVisitUserId]; 
```
{% endtab %}

{% tab title="JS" %}
* 全局配置项 （无）
* 关闭或开启全局数据采集

```javascript
// 开启gdpr，停止数据采集 
window.gio('config',{"dataCollect":"false"}); 
// 关闭gdpr，开始数据采集 
window.gio('config',{"dataCollect":"true"}); // 放在init和send之间 
```

* 获取访问用户 ID

```javascript
window.gio('getVisitUserId'); // 放在send之后
```

* 样例

```javascript
// 开启gdpr，停止数据采集 
window.gio('config',{"dataCollect":"false"}); 
// 关闭gdpr，开始数据采集 
window.gio('config',{"dataCollect":"true"}); 
// 获取访问用户ID 
window.gio('getVisitUserId'); // 放在send之后
```
{% endtab %}
{% endtabs %}

