# 删除子网-DeleteUEdnSubnet

删除子网

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SubnetId|string|子网ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUEdnSubnet
&ProjectId=org-xxx
&SubnetId=uend-subnet-xxx
```

# Response Example
```
{
    "Action": "DeleteUEdnSubnetResponse", 
    "RetCode": 0
}
```

