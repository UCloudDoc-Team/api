# 重启节点-RestartUvodnNode

重启节点v2.0

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NodeId.n|string|节点id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=RestartUvodnNode
&NodeId.0=uedn-node-xxx
&ProjectId=org-xxx
```

# Response Example
```
{
    "Action": "RestartUvodnNodeResponse", 
    "RetCode": 0
}
```

