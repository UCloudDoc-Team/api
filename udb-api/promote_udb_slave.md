# 提升从库-PromoteUDBSlave

从库提升为独立库

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DBId|string|实例的Id,该值可以通过DescribeUDBInstance获取|**Yes**|
|IsForce|bool|是否强制(如果从库落后可能会禁止提升)，默认false 如果落后情况下，强制提升丢失数据|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=PromoteUDBSlave
&Region=cn-bj2
&DBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
&IsForce=true                             
```

# Response Example
```
{
    "Action": "PromoteUDBSlaveResponse", 
    "RetCode": 0
}
```

