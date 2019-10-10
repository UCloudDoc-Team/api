# 将新建的db恢复到指定db某个指定时间点-CreateUDBInstanceByRecovery

创建db，将新创建的db恢复到指定db某个指定时间点

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Name|string|实例名称，至少6位|**Yes**|
|SrcDBId|string|源实例的Id|**Yes**|
|RecoeryTime|int|恢复到某个时间点的时间戳(UTC时间格式，默认单位秒)|**Yes**|
|ChargeType|string|Year， Month， Dynamic，Trial，默认: Dynamic|No|
|Quantity|int|购买时长，默认值1|No|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DBId|string|db实例id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUDBInstanceByRecovery
&Region=cn-bj2
&ChargeType=Month   
&Name=udb-xxxxxxx
&SrcDBId=udb-srcdb
&Time=1432806384
```

# Response Example
```
{
    "Action": "CreateUDBInstanceByRecoveryResponse", 
    "DBId": "00f9868c-c7f5-4852-9eac-d200b678f0e1", 
    "RetCode": 0
}
```

