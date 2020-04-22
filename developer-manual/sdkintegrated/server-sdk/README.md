# 服务端埋点SDK

为了方便您在服务端进行埋点事件的上传，GrowingIO提供了Java和PHP版本的SDK，使您可以像Web和移动端一样，通过几行代码完成埋点事件的上传。

如果您的服务端程序并不是使用这两种语言，您可以使用我们提供的通用接口来实现埋点事件的上报，参考：[埋点事件上传API](../../api-reference/manunl-api.md)

Update：从2020年4月22日起，所有服务端埋点的事件，GrowingIO会自动根据最近4个小时的用户访问记录，关联对应的访问用户ID。从而可以让您通过服务端埋点的事件可以获得更多的分析维度。具体规则请参考：[自动关联访问用户ID](../../api-reference/manunl-api.md#zi-dong-guan-lian-fang-wen-yong-hu-id)

{% page-ref page="java-sdk.md" %}

{% page-ref page="php-sdk.md" %}



