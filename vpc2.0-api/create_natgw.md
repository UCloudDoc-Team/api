# 创建NAT网关-CreateNATGW

创建NAT网关

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NATGWName|string|NAT网关名称|**Yes**|
|SubnetworkIds.n|string|NAT网关绑定的子网Id|**Yes**|
|EIPIds.n|string|NAT网关绑定的EIPId|**Yes**|
|FirewallId|string|NAT网关绑定的防火墙Id|**Yes**|
|VPCId|string|NAT网关所属的VPC Id。默认为Default VPC Id|No|
|IfOpen|int|白名单开关标记。0表示关闭，1表示开启。默认为0|No|
|Tag|string|业务组。默认为空|No|
|Remark|string|备注。默认为空|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|NATGWId|string|申请到的NATGateWay Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateNATGW
&Region=xxx
&ProjectId=xxx
&NATGWName=yNgsbTKP
&SubnetworkIds.n=YLsLksid
&EIPIds.n=hrjFtZYb
&FirewallId=cuUhZpkK
&VPCId=lunRAEbp
&IfOpen=0
&Tag=xwJQsEdL
&Remark=GREoMkdj
```

# Response Example
```
{
    "Action": "CreateNATGWResponse", 
    "RetCode": 0, 
    "NATGWId": "FPvaAtuP"
}
```

