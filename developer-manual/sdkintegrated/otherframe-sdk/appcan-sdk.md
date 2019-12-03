# AppCan埋点SDK

{% hint style="success" %}
API Cloud 全版本支持

App适配最低系统版本：iOS 8及以上、Android 4.2-10
{% endhint %}

## 1. 集成

### 1. 添加自定义插件

插件下载：

* Android：[https://assets.giocdn.com/sdk/android/uexGrowingIO-android-2.6.0.zip](https://assets.giocdn.com/sdk/android/uexGrowingIO-android-2.6.0.zip)
* iOS：[https://assets.giocdn.com/sdk/ios/uexGrowingIO-iOS-2.6.0.zip](https://assets.giocdn.com/sdk/ios/uexGrowingIO-iOS-2.6.0.zip)

在AppCan IDE导航栏中选择”AppCan &gt; 自定义插件 &gt; 添加插件 “，选择对应安装包。

![](../../../.gitbook/assets/image%20%28129%29.png)

### 2. 集成SDK

#### 应用创建



#### 添加跟踪代码

{% tabs %}
{% tab title="Android" %}
Android AppCan集成方式与Android无埋点集成方式不一样，请按照本文集成。

### 1. 添加URL Scheme和权限

将该产品的URL Scheme 添加到您的 AndroidManifest.xml 中的LAUNCHER Activity 下。

代码示例

```javascript
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    package="org.zywx.wbpalmstar.widgetone.uexDemo"
    android:versionCode="1"
    android:versionName="3.0"
    tools:overrideLibrary="org.zywx.wbpalmstar.widgetone.uex">    
    <!-- GrowingIO 需要的权限 -->
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW"/>
    <application
        android:label="Plugin Demo">
        <activity
            android:name="org.zywx.wbpalmstar.engine.LoadingActivity"
            android:configChanges="keyboardHidden|orientation"
            android:launchMode="standard"
            android:screenOrientation="portrait"
            android:theme="@style/browser_loading_theme">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
            <!--GrowingIO 请添加这里的整个 intent-filter 区块，并确保其中只有一个 data 字段-->
            <intent-filter>
                <data android:scheme="growing.您的URL Scheme" />
                <action android:name="android.intent.action.VIEW" />
​
                <category android:name="android.intent.category.DEFAULT" />
                <category android:name="android.intent.category.BROWSABLE" />
            </intent-filter>
            <!--请添加这里的整个 intent-filter 区块，并确保其中只有一个 data 字段-->
        </activity>
        <activity android:name="com.test.HelloAppCanNativeActivity" />
    </application>
</manifest>
```

### 2. 初始化SDK

在 appcan.ready 的时候初始化GrowingIO。

```java
appcan.ready(function() {
    //appcan.initBounce();
    initGio();
})
function initGio() {
    var options = {
        debug : true,
        channel : 'xx应用市场'
    };
    uexGrowingIO.init("您的 ProjectId ", "您的 URL Scheme", options);
}
```
{% endtab %}

{% tab title="iOS" %}
### 1. 添加项目ID

打开项目中的 config.xml 文件

选择底部的”插件AppKey配置”

单击“添加”并修改对应的插件名称为 uexGrowingIO

单击“添加param”，输入键为：$uexGrowingIO\_accountId$，输入值为项目ID。

![](../../../.gitbook/assets/image%20%28152%29.png)

### 2. 添加URL Scheme

打开项目中的 config.xml 文件

选择底部的”插件UrlScheme配置”

在右侧**UrlScheme配置**下配置URL Scheme。

![](../../../.gitbook/assets/image%20%2834%29.png)
{% endtab %}
{% endtabs %}









