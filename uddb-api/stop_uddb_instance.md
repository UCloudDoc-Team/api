# 关闭UDDB实例-StopUDDBInstance

关闭UDDB实例，停止提供服务。

如下状态的UDDB实例可以进行这个操作:

Running: 正常运行中
Abnormal: 异常运行中
当请求返回成功之后，UDDB实例的状态变成"Shutdown"(关闭中); 如果返回失败, UDDB实例状态保持不变 UDDB实例在关闭过程中, 当UDDB实例关闭成功之后, UDDB实例的状态变成"Shutoff"(已关闭); 如果关闭过程中出现异常, 根据UDDB实例的情况, 状态变成"Abnormal"(异常运行中), 或者"Running"(正常运行中)

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|UDDBId|string|UDDB实例ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|如果执行失败, 失败的错误消息|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StopUDDBInstance
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=jqMXBXkT
```

# Response Example
```
{
    "Action": "StopUDDBInstanceResponse", 
    "Message": "WMrpfugk", 
    "RetCode": 0
}
```

