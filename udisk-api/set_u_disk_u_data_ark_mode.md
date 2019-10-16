# 设置UDisk数据方舟的状态-SetUDiskUDataArkMode

设置UDisk数据方舟的状态

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UDiskId|string|需要设置数据方舟的UDisk的Id|**Yes**|
|UDataArkMode|string|是否开启数据方舟，开启:"Yes", 不支持:"No"|**Yes**|

?> "17090": "开启或关闭方舟失败，请稍后再试。"
"17091": "该磁盘距离关闭数据方舟不足三天，无法再次开启"

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=SetUDiskUDataArkMode
&Region=cn-sh2
&Zone=cn-sh2-01
&UDiskId=bs-xxx
&UDiskUDataArkMode=Yes
```

# Response Example
```
{
    "Action": "SetUDiskUDataArkModeResponse", 
    "RetCode": 0
}
```

