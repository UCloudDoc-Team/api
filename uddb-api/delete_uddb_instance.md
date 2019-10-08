# 删除UDDB实例 -DeleteUDDBInstance

删除UDDB实例。
如下状态的UDDB实例可以进行这个操作:
InitFail: 初始化失败
Shutoff: 已关闭
当请求返回成功之后，UDDB实例就已经被删除, 列表上看不到对应的UDDB实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|UDDBId|string|UDDB实例ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|如果执行失败, 失败的错误消息|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUDDBInstance
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=ISYZoije
```

# Response Example
```
{
    "Action": "DeleteUDDBInstanceResponse", 
    "Message": "PseIfuPJ", 
    "RetCode": 0
}
```

