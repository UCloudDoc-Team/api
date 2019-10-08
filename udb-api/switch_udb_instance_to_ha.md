# 普通UDB切换为高可用-SwitchUDBInstanceToHA

普通UDB切换为高可用，原db状态为WaitForSwitch时，调用改api

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|实例的Id,该值可以通过DescribeUDBInstance获取|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DBId|string|切换后高可用db实例的Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=SwitchUDBInstanceToHA
&Region=cn-bj2
&DBId=udb-xxx
```

# Response Example
```
{
    "Action": "SwitchUDBInstanceToHAResponse", 
    "DBId": "udbha-xxxxx", 
    "RetCode": 0
}
```

