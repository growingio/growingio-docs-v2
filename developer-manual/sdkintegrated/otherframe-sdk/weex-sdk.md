# Weex埋点SDK

{% hint style="success" %}
GitHub Demo： [https://github.com/growingio/weex-growingio/tree/master/examples](https://github.com/growingio/weex-growingio/tree/master/examples)

Weex版本支持：0.16.0及以上

App适配最低系统版本：iOS 8及以上、Android 4.2-10
{% endhint %}

{% hint style="warning" %}
为什么不建议圈选Weex实现的界面？

在同时集成**原生无埋点 SDK** 和 **Weex 埋点 SDK** 时， Weex 实现的界面可以圈选， 但是因为本身获取不到元素点击和页面访问事件，所以圈选结果不准确， 只有元素浏览量是真实的，如果想统计相关数据，请使用自定义数据上传发送您需要的数据。 
{% endhint %}

## 集成

{% tabs %}
{% tab title="Android" %}
### 1. 添加Android 原生SDK依赖

* 建议使用 Android Studio 打开项目中， `platforms`文件夹中的`android` 文件夹 。
* Weex 埋点 SDK 是在 Android 原生 SDK 上的扩展，参照 [Android 埋点 SDK](https://docs.growingio.com/docs/sdk-integration/android-sdk/android-mai-dian-sdk#ji-cheng-mai-dian-sdk)，集成步骤的 1~4，操作步骤完全一致。

### 2. 添加SDK

命令行集成：

执行命令`weexpack plugin add weex-growingio`添加采集插件。

手动集成：

在相应工程的 build.gradle 文件的 的 dependencies 中添加

```text
compile 'com.growingio.android:vds-weex:0.3'
```

### 3. 重要配置

和Android 埋点SDK一直，链接 🍎 🍎 
{% endtab %}

{% tab title="iOS" %}
### 1. 添加iOS埋点SDK依赖

Weex埋点 SDK 是在 iOS 原生 SDK 上的扩展，请参照原生iOS SDK &gt; [埋点 SDK集成](../ios-sdk/manunl-ios-sdk.md)，完成代码跟踪部分配置。

### 2. 添加SDK

#### 1. 命令行集成

```text
weex plugin add weex-growingio
```

#### 2. 手动集成 在podfile中添加

```text
pod 'WeexGrowingIO'
```

#### 3. 命令行输入

```text
pod update
```

### 3. 重要配置

与原生混合开发的开发者可详细查看 iOS SDK &gt; 无埋点 SDK 🍎 🍎（无埋点的？） &gt; [重要配置](../ios-sdk/auto-ios-sdk.md#fu-lu-1-zhong-yao-pei-zhi)文档，如果原生控件使用不多，只需关注如下配置即可：

* **​**[**App Store 提交应用注意事项**](../ios-sdk/auto-ios-sdk.md#app-store-ti-jiao-ying-yong-zhu-yi-shi-xiang)\*\*\*\*
{% endtab %}
{% endtabs %}



















