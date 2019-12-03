# 绑定子网的路由表-AssociateRouteTable

绑定子网的路由表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|SubnetId|string|子网ID|**Yes**|
|RouteTableId|string|路由表资源ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=AssociateRouteTable
&ProjectId=eemFmBKl
&Region=TahFeFEn
&RouteTableId=NMUUCFjx
&SubnetId=CmymSJlX
```

# Response Example
```
{
    "Action": "AssociateRouteTableResponse", 
    "RetCode": 0
}
```

