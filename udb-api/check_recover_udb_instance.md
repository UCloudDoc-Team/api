# 核查db是否可以使用回档功能-CheckRecoverUDBInstance

核查db是否可以使用回档功能

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|SrcDBId|string|源实例的Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|LastestTime|int|核查成功返回值为可以回档到的最近时刻,核查失败不返回|No|

# Request Example
```
https://api.ucloud.cn/?Action=CheckRecoverUDBInstance 
&Region=cn-bj2
&SrcDBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
```

# Response Example
```
{
    "Action": "CheckRecoverUDBInstanceResponse", 
    "LastestTime": 1435852800, 
    "RetCode": 0
}
```

