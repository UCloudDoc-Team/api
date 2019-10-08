# 删除项目-TerminateProject

删除项目

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID，请参考[GetProjectList接口](../summary/get_project_list.html)的描述。|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=TerminateProject&ProjectId=acwog
```

# Response Example
```
{
    "Action": "TerminateProjectResponse", 
    "RetCode": 0
}
```

