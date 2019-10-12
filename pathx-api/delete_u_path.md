# 删除UPath-DeleteUPath

删除UPath

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UPathId|string|加速线路实例ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUPath
&ProjectId=org-xxx
&UPathId=upath-xxxx
```

# Response Example
```
{
    "Action": "DeleteUPathResponse", 
    "RetCode": 0
}
```

