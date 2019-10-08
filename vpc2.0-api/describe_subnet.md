# 获取子网信息-DescribeSubnet

获取子网信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|SubnetIds.n|string|子网id数组，适用于一次查询多个子网信息|No|
|SubnetId|string|子网id，适用于一次查询一个子网信息|No|
|VPCId|string|VPC资源id|No|
|Tag|string|业务组名称，默认为Default|No|
|BusinessId|string|业务组|No|
|Offset|int|偏移量，默认为0|No|
|Limit|int|列表长度，默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|子网总数量|**Yes**|
|DataSet|array|子网信息数组，具体资源见下方SubnetInfo|**Yes**|

## SubnetInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|可用区名称|No|
|IPv6Network|string|子网关联的IPv6网段|No|
|OperatorName|string|子网关联的IPv6网段所属运营商|No|
|VPCId|string|VPCId|No|
|VPCName|string|VPC名称|No|
|SubnetId|string|子网Id|No|
|SubnetName|string|子网名称|No|
|Remark|string|备注|No|
|Tag|string|业务组|No|
|SubnetType|int|子网类型|No|
|Subnet|string|子网网段|No|
|Netmask|string|子网掩码|No|
|Gateway|string|子网网关|No|
|CreateTime|int|创建时间|No|
|HasNATGW|bool|是否有natgw|No|
|RouteTableId|string|路由表Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeSubnet
&ProjectId=org-XXXX
&Region=cn-sh2
&SubnetId=subnet-XXX
&VPCId=uvnet-XXXX
&Tag=tag
&Offset=0
&Limit=20
```

# Response Example
```
{
    "Action": "DescribeSubnetResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "VRouterId": "Default_VRouter", 
            "Subnet": "172.16.XXX.0", 
            "Remark": "test", 
            "VPCId": "uvnet-XXXX", 
            "Name": "test-s1", 
            "Zone": "cn-sh2-01", 
            "VPCName": "test", 
            "RouteTableId": "routetable-XXXX", 
            "Gateway": "172.16.XX.1", 
            "SubnetName": "test-s1", 
            "Netmask": "24", 
            "Tag": "Default", 
            "SubnetType": 2, 
            "SubnetId": "subnet-XXXXX", 
            "CreateTime": 1528353483, 
            "HasNATGW": false
        }
    ]
}
```

