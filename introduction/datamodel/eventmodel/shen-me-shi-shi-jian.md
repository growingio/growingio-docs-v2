# 什么是事件

## 事件的定义与产生 <a id="shi-jian-de-ding-yi-yu-chan-sheng"></a>

在GrowingIO的模型中，为了对用户行为进行统计和分析，我们使用一类被称为 "事件" 的消息来记录用户行为。‌

一个事件的产生遵循如下过程：‌

1. GrowingIO的SDK在客户端通过监听等手段捕获各种用户行为
2. SDK将用户行为转化为 "事件" 消息，并发送到GrowingIO服务器

## 事件的组成 <a id="shi-jian-de-zu-cheng"></a>

‌

一个完整的事件应该包含以下几个方面：‌

* 用户信息：描述用户的信息，如：用户ID（访问 or 登录）
* 时间信息：事件发生的时间
* 行为信息：用户做了什么样的行为
* 行为对象信息：用户的行为作用在哪些对象上，比如：点击了按钮 A；浏览了页面 B；修改了文本框 C，那么 A, B, C分别就是用户行为作用对象。

## 事件的类型 <a id="shi-jian-de-lei-xing"></a>

按照事件采集方式的不同，我们将事件分为两大类：‌

### 无埋点事件 <a id="wu-mai-dian-shi-jian"></a>

‌无埋点事件是指用户无需额外开发任何代码，通过集成 GrowingIO SDK ，自动采集生成的事件‌

### 埋点事件 <a id="mai-dian-shi-jian"></a>

埋点事件是指用户通过开发额外的代码，通过调用 GrowingIO SDK 中提供的埋点事件API，来手动向GrowingIO发送的事件。

​[  
](https://app.gitbook.com/@growingio/s/docs/data-model/event-model)

