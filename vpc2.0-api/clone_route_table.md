# 克隆路由表-CloneRouteTable

将现有的路由表复制为一张新的路由表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|RouteTableId|string|被克隆的路由表ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|RouteTableId|string|复制后新的路由表资源ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CloneRouteTable
&ProjectId=RQcXKDep
&RouteTableId=kbDMGqxf
&Region=IvUWkNyp
```

# Response Example
```
{
    "Action": "CloneRouteTableResponse", 
    "RouteTableId": "KxnVuSDD", 
    "RetCode": 0
}
```

