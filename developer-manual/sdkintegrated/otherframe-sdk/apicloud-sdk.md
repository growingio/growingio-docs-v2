# API Cloud埋点SDK

{% hint style="success" %}
GitHub Demo： [https://github.com/growingio/APICloud-growingio/tree/master/android/app](https://github.com/growingio/APICloud-growingio/tree/master/android/app%20%20)

API Cloud 全版本支持

App适配最低系统版本：iOS 8及以上、Android 4.2-10
{% endhint %}

## 1. 配置config.xml文件

名称：GrowingIO

必要参数：accountId、URL Scheme

可选参数：trackerHost、reportHost、dataHost、gtaHost、wsHost、zone

```markup
<feature name="GrowingIO">
<param name="android_accountId" value="xxxxx"/>
<param name="ios_accountId" value="xxxx"/>
<param name="ios_urlScheme" value="xx ios项目的urlScheme  xx"/>
<param name="android_urlScheme" value="xx android项目的urlScheme  xx"/>
<param name="trackerHost" value="xxxxx"/>
<param name="reportHost" value="xxxxx"/>
<param name="dataHost" value="xxxxx"/>
<param name="gtaHost" value="xxxxx"/>
<param name="wsHost" value="xxxxx"/>
<param name="zone" value="xxxxx"/>
<param name="channel" value="xxxx"/>
<param name="debug" value="true or false"/>
</feature>
<preference name="urlScheme" value=" xx ios项目的urlScheme  x " />
<preference name="urlScheme" value=" xx android项目的urlScheme  x " />
```

{% hint style="info" %}
API Cloud的debug模式只支持静态配置，不支持动态配置。
{% endhint %}

## 2. 添加模块

模块包下载：

* iOS模块包：[下载](https://github.com/growingio/APICloud-growingio/blob/master/iOS/iOS/GrowingIO_iOS.zip)​
* Android模块包：[下载](https://github.com/growingio/APICloud-growingio/blob/master/android/GrowingIO.zip)

在API Cloud的开发控制台上选择应用，然后在界面右侧选择 端开发 &gt; 模块。

在应用的模块配置下选择**自定义模块**页签下上传对用模块。

{% hint style="success" %}
* 模块名称需要和zip包名称一致。
* 在自动定义模块中上传了压缩包，保存成功后。一定要点击添加模块后面的“+”，否则不是真正添加成功。添加成功后，去已添加模块中能看到刚刚添加的模块。
{% endhint %}

![](../../../.gitbook/assets/image%20%28194%29.png)

## 3. Android的额外操作

Android云编译Loader为AppLoader， 使用自定义模块时需要编译Android自定义loader, 否则会出现模块未绑定错误, 另外需要注意的是在使用自定义loader时 请勾选 **使用升级环境编译**选项。

具体步骤如下：

1. 在API Cloud的开发控制台上选择应用，然后在界面右侧选择 端开发 &gt; 模块。

在自定义loader页签下勾选**使用升级环境编译**。

![](../../../.gitbook/assets/image%20%28176%29.png)

2. 云编译时，请勾选**使用升级环境编译。**

![](../../../.gitbook/assets/image%20%2869%29.png)

## 4. 插件API

### 初始化 

```javascript
gio.init();
```

       **此接口为Android初始化， 在require后调用，iOS不需要，iOS已自动初始化**建议在require GrowingIO时调用此接口

```javascript
 vargio =null;
 apiready=function(){
     gio =api.require('GrowingIO');
     gio.init();
 }
```

### 设置地理位置

```javascript
gio.setGeoLocation(location);
```

| 参数名   | 类型 | 是否必填   | 参数描述 |
| :--- | :--- | :--- | :--- |
| location | object | 是 | 经纬度 |

调用示例：

```javascript
var gio = api.require('GrowingIO');  //引用模块
var param = {"longitude": longitude, "latitude": latitude}
gio.setGeoLocation(param);
```

### 采集自定义事件

```javascript
gio.track(event, callback);
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;&#x540D;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x586B;</th>
      <th style="text-align:left">&#x53C2;&#x6570;&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">event</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">
        <p>key:eventId(string&#x7C7B;&#x578B;,&#x5FC5;&#x8981;key) value:(string&#x7C7B;&#x578B;)</p>
        <p>key:eventLevelVariable(string&#x7C7B;&#x578B;,&#x975E;&#x5FC5;&#x8981;key)
          value:(object&#x7C7B;&#x578B;)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">callback</td>
      <td style="text-align:left">&#x51FD;&#x6570;</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">
        <p>allback {function (ret)}&#xFF1A;&#x6267;&#x884C;&#x5B8C;&#x8BFB;&#x53D6;&#x64CD;&#x4F5C;&#x540E;&#x7684;&#x56DE;&#x8C03;&#x51FD;&#x6570;&#x3002;</p>
        <p>ret &#x4E3A; callback &#x51FD;&#x6570;&#x7684;&#x53C2;&#x6570;&#xFF0C;&#x6709;&#x4E24;&#x4E2A;&#x5C5E;&#x6027;:</p>
        <p>status:&#x7ED3;&#x679C;2&#x79CD; true, false &#x90FD;&#x4E3A;&#x5E03;&#x5C14;&#x7C7B;&#x578B;</p>
        <p>msg:&#x7ED3;&#x679C;string&#x7C7B;&#x578B;</p>
      </td>
    </tr>
  </tbody>
</table>调用示例：

```javascript
var gio = api.require('GrowingIO');  //引用模块
gio.track({
        eventId: 'GIOKey'
    },function(ret, err){
        //回调函数事件处理
});
```

### 设置转化变量

```javascript
gio.setEvar(conversionVariables,callback);
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;&#x540D;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x586B;</th>
      <th style="text-align:left">&#x53C2;&#x6570;&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">conversionVariables</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">callback</td>
      <td style="text-align:left">&#x51FD;&#x6570;</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">
        <p>callback {function (ret)}&#xFF1A;&#x6267;&#x884C;&#x5B8C;&#x8BFB;&#x53D6;&#x64CD;&#x4F5C;&#x540E;&#x7684;&#x56DE;&#x8C03;&#x51FD;&#x6570;&#x3002;</p>
        <p>ret &#x4E3A;callback &#x51FD;&#x6570;&#x7684;&#x53C2;&#x6570;&#xFF0C;&#x6709;&#x4E24;&#x4E2A;&#x5C5E;&#x6027;:</p>
        <p>status:&#x7ED3;&#x679C;2&#x79CD;true, false &#x90FD;&#x4E3A;&#x5E03;&#x5C14;&#x7C7B;&#x578B;</p>
        <p>msg:&#x7ED3;&#x679C;string&#x7C7B;&#x578B;</p>
      </td>
    </tr>
  </tbody>
</table>调用示例：

```javascript
var gio = api.require('GrowingIO');  //引用模块
gio.setEvar({
           "ekey":"evalue","Date":"2018-07-02"
      },function(ret, err){
           //回调函数事件处理
});
```

### 

### 设置登录用户变量

```javascript
gio.setPeopleVariable(peopleVariables,callback);
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;&#x540D;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x586B;</th>
      <th style="text-align:left">&#x53C2;&#x6570;&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">peopleVariables</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x767B;&#x5F55;&#x7528;&#x6237;&#x53D8;&#x91CF;</td>
    </tr>
    <tr>
      <td style="text-align:left">callback</td>
      <td style="text-align:left">&#x51FD;&#x6570;</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">
        <p>callback {function (ret)}&#xFF1A;&#x6267;&#x884C;&#x5B8C;&#x8BFB;&#x53D6;&#x64CD;&#x4F5C;&#x540E;&#x7684;&#x56DE;&#x8C03;&#x51FD;&#x6570;&#x3002;</p>
        <p>ret &#x4E3A;callback &#x51FD;&#x6570;&#x7684;&#x53C2;&#x6570;&#xFF0C;&#x6709;&#x4E24;&#x4E2A;&#x5C5E;&#x6027;:</p>
        <p>status:&#x7ED3;&#x679C;2&#x79CD;true, false &#x90FD;&#x4E3A;&#x5E03;&#x5C14;&#x7C7B;&#x578B;</p>
        <p>msg:&#x7ED3;&#x679C;string&#x7C7B;&#x578B;</p>
      </td>
    </tr>
  </tbody>
</table>调用示例：

```javascript
var gio = api.require('GrowingIO');  //引用模块
gio.setPeopleVariable({
           "ekey":"evalue","Date":"2018-07-02"
      },function(ret, err){
            //回调函数事件处理
  });
```

### 设置登录用户ID

```javascript
gio.setUserId(userIdObject,callback);
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;&#x540D;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x586B;</th>
      <th style="text-align:left">&#x53C2;&#x6570;&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">userIdObject</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">key:userId(string&#x7C7B;&#x578B;,&#x5FC5;&#x8981;key) value:(string&#x6216;&#x8005;number&#x7C7B;&#x578B;)</td>
    </tr>
    <tr>
      <td style="text-align:left">callback</td>
      <td style="text-align:left">&#x51FD;&#x6570;</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">
        <p>callback {function (ret)}&#xFF1A;&#x6267;&#x884C;&#x5B8C;&#x8BFB;&#x53D6;&#x64CD;&#x4F5C;&#x540E;&#x7684;&#x56DE;&#x8C03;&#x51FD;&#x6570;&#x3002;</p>
        <p>ret &#x4E3A; callback &#x51FD;&#x6570;&#x7684;&#x53C2;&#x6570;&#xFF0C;&#x6709;&#x4E24;&#x4E2A;&#x5C5E;&#x6027;:</p>
        <p>status:&#x7ED3;&#x679C;2&#x79CD;true, false &#x90FD;&#x4E3A;&#x5E03;&#x5C14;&#x7C7B;&#x578B;</p>
        <p>msg:&#x7ED3;&#x679C;string&#x7C7B;&#x578B;</p>
      </td>
    </tr>
  </tbody>
</table>调用示例：

```javascript
var gio = api.require('GrowingIO');  //引用模块
  gio.setUserId({
             "userId":"GIO"
        },function(ret, err){
             //回调函数事件处理
   });
```

### 清除登录用户ID

```javascript
gio.clearUserId(callback);
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;&#x540D;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x586B;</th>
      <th style="text-align:left">&#x53C2;&#x6570;&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">callback</td>
      <td style="text-align:left">&#x51FD;&#x6570;</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">
        <p>callback {function (ret)}&#xFF1A;&#x6267;&#x884C;&#x5B8C;&#x8BFB;&#x53D6;&#x64CD;&#x4F5C;&#x540E;&#x7684;&#x56DE;&#x8C03;&#x51FD;&#x6570;&#x3002;</p>
        <p>ret &#x4E3A;callback &#x51FD;&#x6570;&#x7684;&#x53C2;&#x6570;&#xFF0C;&#x6709;&#x4E24;&#x4E2A;&#x5C5E;&#x6027;:</p>
        <p>status:&#x7ED3;&#x679C;2&#x79CD;true, false &#x90FD;&#x4E3A;&#x5E03;&#x5C14;&#x7C7B;&#x578B;</p>
        <p>msg:&#x7ED3;&#x679C;string&#x7C7B;&#x578B;</p>
      </td>
    </tr>
  </tbody>
</table>调用示例：

```javascript
var gio = api.require('GrowingIO');  //引用模块
gio.clearUserId(function(ret, err){
             //回调函数事件处理
});
```

### 设置访问用户变量

当用户未登录时，定义用户属性变量，也可用于A/B测试上传标签。

```javascript
gio.setVisitor(visitorVar);
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;&#x540D;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x586B;</th>
      <th style="text-align:left">&#x53C2;&#x6570;&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">visitorVar</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">
        <p>&#x4E0D;&#x53EF;&#x4F7F;&#x7528;&#x5D4C;&#x5957;&#x7684;<code>JSONObject</code>&#x5BF9;&#x8C61;&#xFF0C;&#x5373;&#x4E3A;JSONObject&#x4E2D;&#x4E0D;&#x53EF;&#x4EE5;&#x653E;&#x5165;<code>JSONObject</code>&#x6216;&#x8005;<code>JSONArray</code>&#xFF1B;</p>
        <p>key &#x957F;&#x5EA6;&#x9650;&#x5236;&#x5C0F;&#x4E8E;&#x7B49;&#x4E8E;50&#xFF0C;value&#x957F;&#x5EA6;&#x9650;&#x5236;&#x5C0F;&#x7B49;&#x4E8E;1000&#xFF0C;&#x503C;&#x4E0D;&#x80FD;&#x4E3A;&#x7A7A;&#x4E32;&#xFF0C;&#x4E5F;&#x5C31;&#x662F;&quot;&quot;&#x3002;</p>
      </td>
    </tr>
  </tbody>
</table>调用示例：

```javascript
var gio = api.require('GrowingIO');  //引用模块
gio.setVisitor({"gender":"male","age":21});
```

## 常见问题

### 1. 提示无法检测到URL Scheme？

（1）查看 config.xml 是否配置正确。

（2）需要同步代码到云端，云编译生效

### 2. 模拟器无法test？

只能真机测试

### 3. 如何查看发送的数据？

您可以使用GrowingIO官网提供的 [Mobile Debugger](../../debugging/mobile-debugger.md) 工具来查看。

### 4. 此模块是否含有IDFA？

包含IDFA，GrowingIO 使用IDFA 来做来源管理激活设备的精确匹配，让您更好的衡量广告效果。

### 5. 官网Web提示未检测到SDK？

请使用正式版包来操作几次。  






