# 创建子网-CreateUEdnSubnet

创建子网

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|IdcId|string|机房ID|**Yes**|
|CIDR|string|子网cidr|**Yes**|
|SubnetName|string|子网名称|No|
|Comment|string|备注|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|SubnetId|string|子网ID|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUEdnSubnet
&ProjectId=org-xxx
&IdcId=uedn-idc-xxx
&CIDR=10.10.9.0/24
&SubnetName=test-subnet
&Comment=xxx
```

# Response Example
```
{
    "SubnetId": "uedn-subnet-xxx", 
    "Action": "CreateUEdnSubnetResponse", 
    "RetCode": 0
}
```

