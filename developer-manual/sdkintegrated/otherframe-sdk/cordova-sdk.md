# Cordova埋点SDK

{% hint style="success" %}
GitHub Demo：[https://github.com/growingio/Cordova-Demo](https://github.com/growingio/Cordova-Demo) 。

Cordova版本支持：5.0.0及以上

App适配最低系统版本：iOS 8及以上、Android 4.2-10
{% endhint %}

## 集成

### 1. 安装插件

在您项目主目录中执行以下操作：

```text
cordova plugin add cordova-growingio-plugin
```

### 2. 添加跟踪代码

{% tabs %}
{% tab title="Android" %}
添加依赖

* 建议使用 Android Studio 打开项目中， `platforms`文件夹中的`android` 文件夹
* Cordova 埋点 SDK 是在 Android 原生 SDK 上的扩展，参照 Android SDK &gt; [埋点 SDK集成](../android-sdk/manunl-android-sdk.md)，集成步骤的 1~4，操作步骤完全一致。

重要配置

按Android埋点SDK一致。
{% endtab %}

{% tab title="iOS" %}
添加依赖

Cordova 埋点 SDK 是在 iOS 原生 SDK 上的扩展，请参照iOS SDK &gt;  [埋点 SDK集成](../ios-sdk/manunl-ios-sdk.md)，操作完全一致。

重要配置

与原生混合开发的开发者可详细查看 iOS SDK &gt; 无埋点 SDK &gt; [重要配置](../ios-sdk/auto-ios-sdk.md#fu-lu-1-zhong-yao-pei-zhi)文档，如果原生控件使用不多，只需关注如下配置即可：

* **​**[**App Store 提交应用注意事项**](../ios-sdk/auto-ios-sdk.md#app-store-ti-jiao-ying-yong-zhu-yi-shi-xiang)\*\*\*\*
{% endtab %}
{% endtabs %}

## 自定义数据上传

## 常见问题

### 1. 不支持 cordova-plugin-crosswalk-webview 插件

原因：

1. 目前此仓库已经停止维护；
2. 此插件在安卓高版本手机上兼容不好；
3. 内部不是 webview 实现，而是 SurfaceView 。

