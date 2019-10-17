# 创建mongos实例-CreateUDBRouteInstance

创建mongos实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DBTypeId|string|DB类型id，mongodb按版本细分有1：mongodb-2.4，2：mongodb-2.6,3：mongodb-3.0，4：mongodb-3.2|**Yes**|
|Name|string|实例名称，至少6位|**Yes**|
|Port|int|端口号，mongodb默认27017|**Yes**|
|ParamGroupId|int|DB实例使用的配置参数组id|**Yes**|
|MemoryLimit|int|内存限制(MB)，目前支持以下几档 600M/1500M/3000M /6000M/15000M/30000M|**Yes**|
|DiskSpace|int|磁盘空间(GB), 暂时支持20G - 500G|**Yes**|
|ConfigsvrId.n|string|配置服务器的dbid，允许一个或者三个。|**Yes**|
|ChargeType|string|Year， Month， Dynamic，Trial，默认: Month|No|
|Quantity|int|购买时长，默认值1|No|
|UseSSD|bool|是否使用SSD，默认为false|No|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DBId|string|db实例id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUDBRouteInstance
&Region=cn-bj2
&DBTypeId=mongodb-2.6
&ChargeType=Month   
&Name=udb-xxxxxxx
&Port=27017
&ParamGroupId=23
&MemoryLimit=600
&DiskSpace=20
&ConfigsvrId.0=udb-xxxxx
&ConfigsvrId.1=udb-xxxxx
&ConfigsvrId.2=udb-xxxxx
&ShardedClusterId=EmlJjnIa
```

# Response Example
```
{
    "Action": "CreateUDBRouteInstanceResponse", 
    "DBId": "udb-xxxxx", 
    "RetCode": 0
}
```

