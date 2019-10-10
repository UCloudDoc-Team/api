# 节点关机-StopClusterNodeInstance

节点关机

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NodeId|string|Node实例ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|NodeId|string||No|

# Request Example
```
https://api.ucloud.cn/?Action=StopClusterNodeInstance
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-xxx
&NodeId=dnode-xxx
```

# Response Example
```
{
    "Action": "StopClusterNodeInstanceResponse", 
    "RetCode": 0, 
    "NodeId": "dnode-xxx"
}
```

