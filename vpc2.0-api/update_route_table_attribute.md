# 更新路由表基本信息-UpdateRouteTableAttribute

更新路由表基本信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|RouteTableId|string|路由表ID|**Yes**|
|Name|string|名称|No|
|Remark|string|备注|No|
|Tag|string|业务组名称|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateRouteTableAttribute
&ProjectId=UDDWwoDt
&Region=hbZAipNq
&Name=KYKOXPIe
&RouteTableId=wsLpqrtC
&Remark=YpsPZBWg
&Tag=hBPdDMLN
&BusinessId=LvSkWSUA
```

# Response Example
```
{
    "Action": "UpdateRouteTableAttributeResponse", 
    "RetCode": 0
}
```

