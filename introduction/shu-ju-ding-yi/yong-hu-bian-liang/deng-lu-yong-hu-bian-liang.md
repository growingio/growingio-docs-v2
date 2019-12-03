# 登录用户变量

登录用户变量用来保存跟登录用户本身相关的信息，例如用户的姓名，性别，会员卡等级等等。不建议在登录用户变量中保存跟交互行为相关的信息，例如当前正在浏览的商品，当前正在查看的某一个 SaaS 项目。这些随着用户的交互行为会发生变化的信息 GrowingIO 建议使用**页面变量**和**转化变量**来保存。

在某些情况下，某些特定的用户信息会发生变化。例如，某个用户在某天从银卡会员升级成了金卡会员。那么这位用户在银卡会员的时候发生的页面浏览，访问，购买等事件应该归属于银卡会员这个值还是金卡会员这个值呢？这个取决于登录用户变量的归因配置项。

## 登录用户简介 <a id="deng-lu-yong-hu-jian-jie"></a>

登录用户 ID：也就是注册用户 ID，当用户访问您的产品并发生注册/登录行为时，您可以通过 GrowingIO SDK 中的 API 将该用户的注册 ID（或与之对应的唯一标识，可以加密处理）上传给 GrowingIO。

基于登录用户 ID，您可以进行跨平台分析，也可以在登录用户ID 的基础上，将更多的用户个人属性（如：性别、年龄段或您已经分析得出的用户标签）上传给 GrowingIO，从而实现更加高级的业务分析。

更多内容请参考[登录用户模型文档](../../datamodel/usermodel/#deng-lu-yong-hu)。

## 归因模型 <a id="gui-yin-mo-xing"></a>

当发生一个事件的时候，GrowingIO 会通过登录用户变量中配置的归因模型去计算应该将这个事件归到登录用户变量中的哪一个值上，登录用户变量支持两种归因模型：

### **最近（Most Recent）** <a id="zui-jin-most-recent"></a>

当事件发生时，往前看，事件的所有权重全部分配给用户变量中**离事件发生的时间最近的值**上。例如，在前面的某个用户在某天从银卡升级成为金卡的例子中，在最近这种归因模型下，所有银卡时候发生的页面浏览，访问，购买事件等等都仍然归到银卡上。

### 最终（Final） <a id="zui-zhong-final"></a>

当事件发生时，往后看，事件的所有权重全部分配给用户变量中**最终设置的值**上。例如，在前面的某个用户在某天从银卡升级成为金卡的例子中，在最终这种归因模型下，所有银卡时候发生的页面浏览，访问，购买事件等等都会归到金卡上。

## 配置和上传 <a id="pei-zhi-he-shang-chuan"></a>

### **第一步：在 “事件和变量”中完成配置** <a id="di-yi-bu-zai-shi-jian-he-bian-liang-zhong-wan-cheng-pei-zhi"></a>

具体的将自定义变量添加到网站或者移动应用上之前，GrowingIO 要求先在打点管理的界面上进行变量的声明操作，然后再开展具体的添加自定义变量的操作。

配置方式参考[用户变量](../../../product-manual/datacenter/datamanage/variable/user.md)。

### **第二步：代码部署** <a id="di-er-bu-dai-ma-bu-shu"></a>

完成了配置后，即可在代码中完成以上设计的 “自定义事件和变量” 的部署。具体的说，就是调用 GrowingIO 提供的 API 接口，上传数据。

* ​[JS 接口文档​](../../../developer-manual/sdkintegrated/web-js-sdk/web-sdk-api/)
* ​[Android 接口文档​](../../../developer-manual/sdkintegrated/android-sdk/android-sdk-api/)
* ​[iOS 接口文档​](../../../developer-manual/sdkintegrated/ios-sdk/ios-sdk-api/)
* [​小程序、小游戏以及内嵌页 SDK​](../../../developer-manual/sdkintegrated/other-sdk/customize-api.md)

API中给出了登录用户变量的上传方式

### 第三步：数据校验 <a id="di-san-bu-shu-ju-xiao-yan"></a>

在完成了GrowingIO平台的配置，以及代码实施后，我们当然需要对数据是否成功上传进行校验。校验工作分为两步完成。

#### **数据校验第一步：本地开发环境校验** <a id="shu-ju-xiao-yan-di-yi-bu-ben-di-kai-fa-huan-jing-xiao-yan"></a>

GrowingIO 提供了 SDK debug 模式以及 debug 工具，来帮助您完成数据的校验。具体请参考 [Debugger 最佳实践](https://docs.growingio.com/docs/sdk-integration/growingio-debugger/best-practice#ppl-yong-hu-bian-liang-shi-jian)。

#### **数据校验第二步：GrowingIO 后台图表验证** <a id="shu-ju-xiao-yan-di-er-bu-growingio-hou-tai-tu-biao-yan-zheng"></a>

在 GrowingIO 分析后台，找到 “分析” - “新建事件分析”，选择一个事件后，在 "维度" 中查看设置的登录用户变量是否有数据。当然，您需要首先确已经完成了登录用户变量的数据上传。

至此，您已经完成了 “自定义变量” 的上传，如您在配置或添加代码中有任何疑问，请联系您的客户成功经理咨询，或在工单系统中反馈问题。谢谢。

## **用户变量的持久性范围** <a id="yong-hu-bian-liang-de-chi-jiu-xing-fan-wei"></a>

登录用户变量默认的持久性范围是永远。当某个用户配置上某一个用户变量的某一个值时，如果后面没有再修改，那么这个用户在今后会一直保持这个值。也就是说，用户在之后不管多久的时间段内发生的各种各样的事件都可以归到这个登录用户变量的值上，除非之后显式的更改了这个登录用户变量的值。

