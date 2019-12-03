# 埋点SDK支持的其他接口

{% hint style="info" %}
**GrowingIO 埋点 SDK 仅自动采集设备信息和您埋点内容数据，对比无埋点 SDK ，埋点 SDK 少很多 API， 请勿在埋点 SDK 中调用无埋点 SDK 接口。**
{% endhint %}

```java
1，若使用加密功能,请在UI元素初始化之前设置此函数
+ (void)setEncryptStringBlock:(NSString*(^)(NSString*string))block;
​
2，deeplink广告落地页参数回调设置
+ (void)registerDeeplinkHandler:(void(^)(NSDictionary*params, NSError*error))handler;
​
3，Universallink广告落地页参数回调设置
+ (void)registerUniversallinkHandler:(void(^)(NSDictionary*params, NSError*error))handler;
​
4，该函数请在main函数第一行调用APP启动后将不允许修改采集模式
+ (void)setAspectMode:(GrowingAspectMode)aspectMode;
+ (GrowingAspectMode)getAspectMode;

5，设置发送数据的时间间隔（单位为秒）
+ (void)setFlushInterval:(NSTimeInterval)interval;
+ (NSTimeInterval)getFlushInterval;
```

