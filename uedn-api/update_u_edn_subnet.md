# 更新子网信息-UpdateUEdnSubnet

更新子网信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SubnetId|string|子网ID|**Yes**|
|SubnetName|string|子网名称|No|
|Comment|string|备注|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateUEdnSubnet
&ProjectId=org-xxx
&SubnetId=uedn-subnet-xxx
&SubnetName=xxx
&Comment=xxx
```

# Response Example
```
{
    "Action": "UpdateUEdnSubnetResponse", 
    "RetCode": 0
}
```

