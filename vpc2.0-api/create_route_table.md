# 创建路由表-CreateRouteTable

创建路由表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|VPCId|string|所属的VPC资源ID|**Yes**|
|Name|string|路由表名称。默认为RouteTable|No|
|Tag|string|路由表所属业务组|No|
|Remark|string|备注|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|RouteTableId|string|路由表ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateRouteTable
&ProjectId=LkJMALSJ
&Region=qnQpINtC
&Name=bvCyxghX
&VPCId=bXziHrsy
&Tag=IEyWXftj
&Remark=RQGLrZBh
&BusinessId=RpgaqMhT
```

# Response Example
```
{
    "Action": "CreateRouteTableResponse", 
    "RouteTableId": "mJzMtPHJ", 
    "RetCode": 0
}
```

