# 修改加速线路带宽-ModifyUPathBandwidth

修改加速线路带宽

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|UPathId|string|加速线路Id|**Yes**|
|Bandwidth|string|带宽|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyUPathBandwidth
&UPathId=upath-xxx
&Bandwidth=10
```

# Response Example
```
{
    "Action": "ModifyUPathBandwidthResponse", 
    "RetCode": 0
}
```

