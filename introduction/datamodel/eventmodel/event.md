# 什么是事件

## 事件的定义与产生 <a id="shi-jian-de-ding-yi-yu-chan-sheng"></a>

在GrowingIO的模型中，为了对用户行为进行统计和分析，我们使用一类被称为 "事件" 的消息来记录用户行为。‌

一个事件的产生遵循如下过程：‌

1. GrowingIO的SDK在客户端通过监听等手段捕获各种用户行为
2. SDK将用户行为转化为 "事件" 消息，并发送到GrowingIO服务器

## 事件的组成 <a id="shi-jian-de-zu-cheng"></a>

一个完整的事件应该包含以下几个方面：‌

* 用户信息：描述用户的信息，如：用户ID（访问 or 登录）
* 时间信息：事件发生的时间
* 行为信息：用户做了什么样的行为
* 行为对象信息：用户的行为作用在哪些对象上，比如：点击了按钮 A；浏览了页面 B；修改了文本框 C，那么 A, B, C分别就是用户行为作用对象。

## 采集事件的类型 <a id="shi-jian-de-lei-xing"></a>

按照事件采集方式的不同，我们将事件分为两大类：‌

### 无埋点事件 <a id="wu-mai-dian-shi-jian"></a>

‌无埋点事件是指用户无需额外开发任何代码，通过集成 GrowingIO SDK ，自动采集生成的事件‌。

| 事件名称 | 发送时机 | t 字段值 |
| :--- | :--- | :--- |
| page 事件 | 每当进入一个页面时会发送一个page事件 | page |
| vst 事件 | 每当产生一个新的访问时 | vst |
| activate 事件 | 当 App 首次激活打开时 | avtivate |
| reengage 事件 | 由 GrowingIO Deep Link 唤醒App时 | reengage |
| clck 事件 | 当用户对 App 上的可点击元素有点击行为时 | clck |
| imp 事件 | 当有元素展现时 | imp |
| chng 事件 | 当用户对 App 上的输入元素有改变的行为时 | chng |

### 埋点事件 <a id="mai-dian-shi-jian"></a>

埋点事件是指用户通过开发额外的代码，通过调用 GrowingIO SDK 中提供的埋点事件API，来手动向GrowingIO发送的事件。

| 事件名称 | 发送时机 | t 字段值 | var 字段值 | 其它字段 |
| :--- | :--- | :--- | :--- | :--- |
| cstm 事件 | 调用 track 类型的接口时 | cstm | 若您设置了事件级变量 | n 为事件标识符 |
| pvar 事件 | 调用 setPageVariable 接口时 | pvar | 若您设置了页面级变量 | 无 |
| evar 事件 | 调用 setEvar 类型接口时 | evar | 若您设置了转化变量 | 无 |
| ppl 事件 | 调用 setPeopleVariable 类型的接口时 | ppl | 若您设置了用户变量 | 无 |
| vstr 事件 | 调用 setVisitor 类型接口时 | vstr | 若您设置了访问用户变量 | 无 |

