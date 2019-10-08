# 创建子网-CreateSubnet

创建子网

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|VPCId|string|VPC资源ID|**Yes**|
|Subnet|string|子网网络地址，例如192.168.0.0|**Yes**|
|Netmask|int|子网网络号位数，默认为24|No|
|SubnetName|string|子网名称，默认为Subnet|No|
|Tag|string|业务组名称，默认为Default|No|
|Remark|string|备注|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|SubnetId|string|子网ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateSubnet
&ProjectId=org-XXXXX
&Region=cn-sh2
&VPCId=vnet-XXXX
&Subnet=10.1.1.0
&Netmask=24
&SubnetName=test
&Tag=test
&Remark=test
&BusinessId=test
```

# Response Example
```
{
    "SubnetId": "subnet-XXXXX", 
    "Action": "CreateSubnetResponse", 
    "RetCode": 0
}
```

