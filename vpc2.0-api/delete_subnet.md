# 删除子网-DeleteSubnet

删除子网

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|SubnetId|string|子网ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteSubnet
&ProjectId=org-XXXX
&Region=cn-sh2
&SubnetId=subnet-XXXXX
```

# Response Example
```
{
    "Action": "DeleteSubnetResponse", 
    "RetCode": 0
}
```

