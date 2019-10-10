# 核查db是否可以升级为高可用-CheckUDBInstanceToHAAllowance

核查db是否可以升级为高可用

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DBId|string|实例的Id,该值可以通过DescribeUDBInstance获取|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Allowance|string|Yes ，No ，Yes即可以升级，No为不可以升级|No|

# Request Example
```
https://api.ucloud.cn/?Action=CheckUDBInstanceToHAAllowance
&Region=cn-bj2
&DBId=udb-xxxxx
```

# Response Example
```
{
    "Action": "CheckUDBInstanceToHAAllowanceResponse", 
    "RetCode": 0, 
    "Allowance": "Yes"
}
```

