# 获取配置文件内容-ExtractUDBParamGroup

获取配置文件内容

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|GroupId|int|配置id|**Yes**|
|RegionFlag|bool|是否跨可用区，RegionFlag为true时表示跨可用区配置文件|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Content|string|配置文件内容|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ExtractUDBParamGroup
&Region=cn-zj
&Zone=cn-zj-01
&GroupId=9
&RegionFlag=false
```

# Response Example
```
{
    "Content": "MEuQwaaA", 
    "Action": "ExtractUDBParamGroupResponse", 
    "RetCode": 0
}
```

