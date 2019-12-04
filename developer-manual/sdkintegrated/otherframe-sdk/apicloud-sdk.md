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

![](../../../.gitbook/assets/image%20%28192%29.png)

## 3. Android的额外操作

Android云编译Loader为AppLoader， 使用自定义模块时需要编译Android自定义loader, 否则会出现模块未绑定错误, 另外需要注意的是在使用自定义loader时 请勾选 **使用升级环境编译**选项。

具体步骤如下：

1. 在API Cloud的开发控制台上选择应用，然后在界面右侧选择 端开发 &gt; 模块。

在自定义loader页签下勾选**使用升级环境编译**。

![](../../../.gitbook/assets/image%20%28174%29.png)

2. 云编译时，请勾选**使用升级环境编译。**

![](../../../.gitbook/assets/image%20%2867%29.png)

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






