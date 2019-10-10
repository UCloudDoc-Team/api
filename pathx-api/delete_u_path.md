# 删除UPath-DeleteUPath

删除UPath

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|UPathId|string|加速线路id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUPath
&UPathId=jWeXMMrv
```

# Response Example
```
{
    "Action": "DeleteUPathResponse", 
    "RetCode": 0
}
```

