# 更新NAT网关绑定的子网-UpdateNATGWSubnet

更新NAT网关绑定的子网

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|NATGWId|string|NAT网关Id|**Yes**|
|SubnetworkIds.n|string|NAT网关绑定的子网Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateNATGWSubnet
&Region=xxx
&ProjectId=xxx
&NATGWId=BKyXAAfg
&SubnetworkIds.0=ShexPLKL
```

# Response Example
```
{
    "Action": "UpdateNATGWSubnetResponse", 
    "RetCode": 0
}
```

