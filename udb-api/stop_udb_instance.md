# 关闭云数据库-StopUDBInstance

关闭UDB实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DBId|string|实例的Id,该值可以通过DescribeUDBInstance获取|**Yes**|
|ForceToKill|bool|是否使用强制手段关闭DB，默认是false|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StopUDBInstance   
&Region=cn-bj2
&DBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
```

# Response Example
```
{
    "Action": "StopUDBInstanceResponse", 
    "RetCode": 0
}
```

