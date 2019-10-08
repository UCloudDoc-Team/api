# 获取最早可回档时间-FetchUDBInstanceEarliestRecoverTime

获取UDB最早可回档的时间点

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|DB实例Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|EarliestTime|int|获取最早可回档时间点|No|

# Request Example
```
https://api.ucloud.cn/?Action=FetchUDBInstanceEarliestRecoverTime
&Region=cn-bj2
&DBId=2bbf9968-2ded-48c5-89c0-4f4d683bdd6c
```

# Response Example
```
{
    "Action": "FetchUDBInstanceEarliestRecoverTimeResponse", 
    "EarliestTime": 1457680002, 
    "RetCode": 0
}
```

