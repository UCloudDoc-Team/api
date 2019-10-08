# 展示NAT网关可绑定的子网列表-ListSubnetForNATGW

展示NAT网关可绑定的子网列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|VPCId|string|NAT网关所属VPC Id。默认值为Default VPC Id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|具体参数请见NatgwSubnetDataSet|No|

## NatgwSubnetDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SubnetId|string|子网id|**Yes**|
|Subnet|string|子网网段|**Yes**|
|Netmask|string|掩码|**Yes**|
|SubnetName|string|子网名字|**Yes**|
|HasNATGW|bool|是否绑定NATGW|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ListSubnetForNATGW
&Region=xxx
&ProjectId=xxx
&VPCId=uAfTvSwq
```

# Response Example
```
{
    "Action": "ListSubnetForNATGWResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "SubnetId": "xxxx", 
            "Subnet": "xxxx", 
            "Netmask": "xxxx", 
            "SubnetName": "xxxx", 
            "HasNATGW": "xxxx"
        }
    ]
}
```

