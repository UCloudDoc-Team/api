# 更新USQL设置-UpdateUSQLSetting

更新用户的USQL设置信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|OutputLocation|string|结果输出位置|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|OutputLocation|string|结果输出位置|**Yes**|
|Request|string|API请求ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateUSQLSetting
&Region=cn-bj2
&OutputLocation=ufile://usql-bucket/my-object.csv
&ProjectId=org-32812
```

# Response Example
```
{
    "Action": "UpdateUSQLSettingResponse", 
    "Request": "TJCzNJGt", 
    "OutputLocation": "ufile://usql-bucket/my-object.csv", 
    "RetCode": 0
}
```

