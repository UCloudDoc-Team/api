# 更新子网信息-UpdateSubnetAttribute

更新子网信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SubnetId|string|子网ID|**Yes**|
|Name|string|子网名称(如果Name不填写，Tag必须填写)|No|
|Tag|string|业务组名称(如果Tag不填写，Name必须填写)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateSubnetAttribute
&Region=cn-sh2
&ProjectId=org-XXXX
&SubnetId=subnet-XXXXX
&Name=test
&Tag=test
```

# Response Example
```
{
    "Action": "UpdateSubnetAttributeResponse", 
    "RetCode": 0
}
```

