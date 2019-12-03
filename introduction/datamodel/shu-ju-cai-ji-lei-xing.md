# 数据采集类型

GrowingIO会采集两种类型的时间类型。

#### 类型一：无埋点事件类型列表 <a id="lei-xing-yi-wu-mai-dian-shi-jian-lei-xing-lie-biao"></a>

| 事件名称 | 发送时机 | t 字段值 |
| :--- | :--- | :--- |
| page 事件 | 每当进入一个页面时会发送一个page事件 | page |
| vst 事件 | 每当产生一个新的访问时 | vst |
| activate 事件 | 当 App 首次激活打开时 | avtivate |
| reengage 事件 | 由 GrowingIO Deep Link 唤醒App时 | reengage |
| clck 事件 | 当用户对 App 上的可点击元素有点击行为时 | clck |
| imp 事件 | 当有元素展现时 | imp |
| chng 事件 | 当用户对 App 上的输入元素有改变的行为时 | chng |

#### 类型二：埋点事件类型列表 <a id="lei-xing-er-mai-dian-shi-jian-lei-xing-lie-biao"></a>

| 事件名称 | 发送时机 | t 字段值 | var 字段值 | 其它字段 |
| :--- | :--- | :--- | :--- | :--- |
| cstm 事件 | 调用 track 类型的接口时 | cstm | 若您设置了事件级变量 | n 为事件标识符，num为事件数值 |
| pvar 事件 | 调用 setPageVariable 接口时 | pvar | 若您设置了页面级变量 | 无 |
| evar 事件 | 调用 setEvar 类型接口时 | evar | 若您设置了转化变量 | 无 |
| ppl 事件 | 调用 setPeopleVariable 类型的接口时 | ppl | 若您设置了用户变量 | 无 |
| vstr 事件 | 调用 setVisitor 类型接口时 | vstr | 若您设置了访问用户变量 | 无 |

