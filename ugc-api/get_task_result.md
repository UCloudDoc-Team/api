# 获取异步任务结果-GetTaskResult

获取异步任务的运行结果，该接口请求地址是api.ugc.service.ucloud.cn。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|TaskId|string|任务ID	|**Yes**|
|AccessToken|string|授权Token	|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|错误原因|**Yes**|
|State|string|任务运行状态,Running：运行中;Success：成功;Fail：失败|**Yes**|

# Request Example
```
http(s)://api.ugc.service.ucloud.cn/?Action=GetTaskResult
&Region=cn-bj2
&TaskId=123456
```

# Response Example
```
{
    "Action": "GetTaskResultResponse", 
    "Message": "jtumyFth", 
    "State": "mcPxKxcD", 
    "RetCode": 0
}
```

