# 埋点 SDK集成

埋点 SDK 的目标用户是使用第三方插件开发的 APP， 比如使用 Weex、APICloud 等。在这些平台中，我们无法自动采集用户的点击事件和页面浏览事件等，需要依赖调用自定义事件和变量 API来进行数据采集。 如果您的 APP 使用 iOS 原生开发，并且希望自动采集用户的点击事件、页面浏览事件等无埋点事件， 请集成 iOS 无埋点SDK 。

前提条件

* 获取项目ID，获取方法请参考"项目管理 &gt; 项目概览 &gt; [查看项目基本信息](../../../product-manual/sysmanage/projectmange/details.md#cha-kan-xiang-mu-ji-ben-xin-xi)"。
* 获取URL Scheme，在GrowingIO平台创建对应的应用时会生成URL Scheme。请参考[创建应用](../../../product-manual/sysmanage/projectmange/application-manage.md#chuang-jian-ying-yong)。

## 1. 添加跟踪代码

{% hint style="success" %}
集成环境：Xcode 9.0及以上；

App适配最低系统版本：iOS 8及以上
{% endhint %}

**组件化SDK**

GrowingIO iOS SDK 2.8.7 包含以下组件SDK:

• GrowingCoreKit \(组件基础库,具备分析功能\)

{% hint style="warning" %}
请保证Growing、GrowingCoreKit版本号一致
{% endhint %}

### 1. 添加依赖

{% tabs %}
{% tab title="使用CocoaPods快速添加" %}
1. 在您的Podfile中添加`pod 'GrowingCoreKit'`。
2. 执行`pod install` 或 `pod update` 更新pod依赖库。
3. （可选）GrowingIO推荐您添加 **AdSupport.framework** 依赖库，用于来源管理激活匹配,有利于您更好的分析数据 ,添加项目依赖库的位置在项目设置target -&gt; 选项卡General -&gt; Linked Frameworks and Libraries
{% endtab %}

{% tab title="手动添加" %}
1. 下载iOS SDK以下包：[GrowingHeader](https://assets.growingio.com/sdk/ios/GrowingIO-iOS-PublicHeader-2.8.7.zip) ，[GrowingCoreKit](https://assets.growingio.com/sdk/ios/GrowingIO-iOS-CoreKit-2.8.7.zip)，并解压。
2. 将`Growing.h`、`GrowingCoreKit.framework`、添加到iOS工程中。

{% hint style="info" %}
提醒：记得勾选”Copy item if needed“
{% endhint %}

3. 在工程项目中添加以下库文件

> 添加项目依赖库的位置在项目设置target -&gt; 选项卡General -&gt; Linked Frameworks and Libraries

| 库名称 | 说明 |
| :--- | :--- |
| Foundation.framework | 基础依赖库 |
| Security.framework | 用于APP连接圈选页面SSL连接 |
| CoreTelephony.framework | 用于读取运营商名称 |
| SystemConfiguration.framework | 用于判断网络状态 |
| AdSupport.framework | 用于来源管理激活匹配 |
| libicucore.tbd | 用于WebSocket |
| libsqlite3.tbd | 存储日志 |
| CoreLocation.framework | 用于读取地理位置信息（如果您的app有权限） |
| JavaScriptCore.framework | Web圈App交互 |
| WebKit.framework | Web圈选 |

4. 添加编译参数，并注意大小写。

![](../../../.gitbook/assets/image%20%2884%29.png)
{% endtab %}
{% endtabs %}

### 2. 添加 URL Scheme

添加URL Scheme 到项目中，以便唤醒您的程序进行圈选。

![](../../../.gitbook/assets/image%20%2873%29.png)

### 3. 初始化配置

> 在 AppDelegate 中引入`#import "Growing.h"`并添加初始化方法。

```swift
#import "Growing.h"
- (BOOL)application:(UIApplication *)application
didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
  ...
  // 启动GrowingIO

   [Growing startWithAccountId:@"您的项目ID"];      // 替换为您的项目ID
      // 其他配置
      // 开启Growing调试日志 可以开启日志
      // [Growing setEnableLog:YES];
```

{% hint style="warning" %}
请确保将代码添加在上述位置，添加到其他方法或异步block中可能导致数据不准确。
{% endhint %}

### 4.添加代码

{% hint style="warning" %}
因为您代码的复杂程度以及iOS SDK的版本差异，有时候 \[Growing handleUrl:url\] 并没有被调用。请在各个平台上调试这段代码，确保当App被URL scheme唤醒之后，该函数能被调用到。
{% endhint %}

```swift
- (BOOL)application:(UIApplication *)application openURL:(NSURL *)url sourceApplication:(NSString *)sourceApplication annotation:(id)annotation
{
    ...
 if ([Growing handleUrl:url]) // 请务必确保该函数被调用
  {
      return YES;
  }
  return NO;
 ...
}
```

{% hint style="warning" %}
### 提醒：

* 若您在 AppDelegate 中实现了以下一个或多个方法，请在已实现的函数中，调用`[Growing handleUrl:]`

  ```objectivec
  - (BOOL)application:(UIApplication *)application openURL:(NSURL *)url sourceApplication:(nullable NSString *)sourceApplication annotation:(id)annotation
  - (BOOL)application:(UIApplication *)application handleOpenURL:(NSURL *)url
  - (BOOL)application:(UIApplication *)app openURL:(NSURL *)url options:(NSDictionary<NSString*, id> *)options
  ```

* 若以上所有方法均未实现，请实现以下方法并调用`[Growing handleUrl:]`

  ```objectivec
  - (BOOL)application:(UIApplication *)application openURL:(NSURL *)url sourceApplication:(nullable NSString *)sourceApplication annotation:(id)annotation
  ```

* 实际情况可能很复杂，请在调试时确保函数`[Growing handleUrl:]`会被执行到
{% endhint %}

## 3. App Store提交应用注意事项

如果您添加了库**AdSupport.framework**, GrowingIO则会启用 IDFA，所以在向 App Store 提交应用时，需要：

* 对于问题 **Does this app use the Advertising Identifier \(IDFA\)**，选择 **YES**。
* 对于选项**Attribute this app installation to a previously served advertisement**，打勾。
* 对于选项**Attribute an action taken within this app to a previously served advertisement**，打勾。

> **为什么 GrowingIO 使用 IDFA?** GrowingIO 使用 IDFA 来做来源管理激活设备的精确匹配，让你更好的衡量广告效果。如果您不希望启用IDFA，可以选择不引入 AdSupport.framework

## 4. 自定义数据上传

除上述的用户行为数据（无埋点数据）之外，GrowingIO 还提供了多种 API 接口，供您上传一些自定义的数据指标及维度 ，请参考iOS SDK API &gt; [自定义数据上传API](ios-sdk-api/customize-api.md) 。

## 5. 创建应用 <a id="4-chuang-jian-ying-yong"></a>

**添加代码之后，请先Clean项目，然后再进行编译，并在你的 Android App 安装了 SDK 后重新启动几次 App，保证行为采集数据自动发送给 GrowingIO，以便顺利完成检测。**

 在GrowingIO平台的应用创建页面继续完成应用创建的数据检测，检测成功后应用创建成功。

## 6. 验证SDK是否正常采集数据 <a id="5-yan-zheng-sdk-shi-fou-zheng-chang-cai-ji-shu-ju"></a>

了解GrowingIO平台数据采集类型请参考[数据模型](../../../introduction/datamodel/)。

GrowingIO为您提供多种验证SDK是否正常采集数据的方式：

方式一：[Mobile Debugger](../../debugging/mobile-debugger.md)​

方式二：在SDK中设置了Debug模式后，在IDE编译器控制台查看数据采集日志。

方式三：[数据校验](../../../product-manual/datacenter/datacheck.md)

