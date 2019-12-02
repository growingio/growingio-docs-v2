# Flutter埋点SDK

{% hint style="success" %}
GitHub Demo：[https://github.com/growingio/flutter-growingio-track/tree/develop/example](https://github.com/growingio/flutter-growingio-track/tree/develop/example)。

App适配最低系统版本：iOS 8及以上、Android 4.2-10
{% endhint %}

## 集成

### 1. Flutter插件获取安装

根据[dart pub](https://pub.dartlang.org/packages/flutter_growingio_track#-installing-tab-)文档获取安装。

### 2. 添加跟踪代码

{% tabs %}
{% tab title="Android（Native部分）" %}
Flutter插件运行在Android手机上时依赖于GrowingIO Android SDK \(可以是无埋 点SDK也可以是埋点SDK\)2.6.0及以上, 原生部分请参考：

Android SDK &gt; [无埋点 SDK集成](../android-sdk/auto-android-sdk.md)

Android SDK &gt; [埋点 SDK集成](../android-sdk/manunl-android-sdk.md) 
{% endtab %}

{% tab title="iOS（Native部分）" %}
Flutter 埋点插件是在iOS原生SDK上的扩展，请参考 iOS SDK &gt; [埋点 SDK集成](../ios-sdk/manunl-ios-sdk.md)。 🍎 🍎 无埋点不可以吗？？？
{% endtab %}
{% endtabs %}

## 常见问题

### 1. iOS ：App Store 提供应用注意事项---- 🍎 这个注意事项是Flutter独有的吗？？？

如果您添加了库AdSupport.framework, GrowingIO则会启用IDFA，所以在向App Store 提交应用时，需要：

* 对于问题Does this app use the Advertising Identifier \(IDFA\)，选择YES。
* 对于选项Attribute this app installation to a previously served advertisement，打勾。
* 对于选项Attribute an action taken within this app to a previously served advertisement，打勾。

### 2. iOS：为什么GrowingIO使用IDFA？---- 🍎 同上

GrowingIO 使用IDFA 来做来源管理激活设备的精确匹配，让你更好的衡量广告效果。如果你不希望跟踪这个信息，可以选择不引入AdSupport.framework

### 3. 初始化Android SDK时，GrowingIO类可能会报红色怎么处理？

这个应该是Flutter项目结构的问题，并不影响运行，可以放心编译. 不过需要手动import。 🍎 🍎 本章节接口内容都有下面的这个import，API内容要提到公共节点，这个引入怎么在本文进行说明？？？

```java
import 'package:growingioflutter/growingio_track.dart';
```

### 4. 为什么不在Flutter中单独初始化？

* 因为GrowingIO需要获取Android的Activity生命周期，为了数据的准确性，需要在Activity出现前就初始化完成
* 开发者相信很多用户都会使用flutter + native形式的进行开发，为了同时服务flutter于native

####   <a id="43-android-chu-shi-hua-android-sdk-shi-growingio-lei-ke-neng-hui-bao-hong-se"></a>

