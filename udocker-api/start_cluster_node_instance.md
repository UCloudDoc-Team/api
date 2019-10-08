# 启动节点-StartClusterNodeInstance

启动节点

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|NodeId|string|Node实例ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|NodeId|string|节点ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=StartClusterNodeInstance
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-xxx
&NodeId=dnode-xxx
```

# Response Example
```
{
    "Action": "StartClusterNodeInstanceResponse", 
    "RetCode": 0, 
    "NodeId": "dnode-xxx"
}
```

