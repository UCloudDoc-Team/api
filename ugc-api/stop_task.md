# 停止异步任务-StopTask

用于停止异步任务

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|TaskId|string|异步任务ID|**Yes**|
|AccessToken|string|UGC提交任务Token，通过GetAccessToken获得|**Yes**|

?> 必须在内网调用，不通过api.ucloud.cn

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|RetCode|int|返回码|**Yes**|
|Message|string|描述信息|**Yes**|
|TaskId|string|所操作的TaskId|No|

# Request Example
```
http(s)://api.ugc.service.ucloud.cn/?Action=StopTask
&Region=cn-bj2
&TaskId=d9cb5d99309dce06e0a7adb850878a4635daf49a82145e0637542f8763bff90e
&AccessToken=H2JKDKOW3HN24CGG1PV3DV779932C
```

# Response Example
```
{
    "Action": "StopTaskResponse", 
    "Message": "pUFDfSiL", 
    "RetCode": 0
}
```

