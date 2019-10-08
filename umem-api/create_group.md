# 创建主备redis-CreateURedisGroup

创建主备redis

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Name|string|请求创建组的名称 (范围[6-63],只能包含英文、数字以及符号-和_)|**Yes**|
|HighAvailability|string|是否开启高可用,enable或disable|**Yes**|
|Size|int|每个节点的内存大小,单位GB,默认1GB,目前仅支持1/2/4/8/16/32,六种|No|
|AutoBackup|string|是否自动备份,enable或disable，默认disable|No|
|BackupTime|int|自动备份开始时间,范围[0-23],默认3点|No|
|ConfigId|string|配置ID,目前仅支持默认配置id 默认配置id:"03f58ca9-b64d-4bdd-abc7-c6b9a46fd801"|No|
|Version|string|Redis版本信息(详见DescribeURedisVersion返回结果),默认版本3.0|No|
|ChargeType|string|计费模式，Year , Month, Dynamic 默认: Month|No|
|Quantity|int|购买时长，默认为1|No|
|Tag|string|业务组名称|No|
|Password|string|初始化密码,需要 base64 编码|No|
|BackupId|string|有此项代表从备份中创建，无代表正常创建|No|
|SlaveZone|string|跨机房URedis，slave所在可用区（必须和Zone在同一Region，且不可相同）|No|
|MasterGroupId|string|Master Redis Group的ID，创建只读Slave时，必须填写|No|
|CouponId|string|代金券ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|GroupId|string|创建的组ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateURedisGroup
&Region=cn-bj2
&Zone=cn-bj2-04
&Name=zb_redisXXXX
&Protocol=GSlQEcQU
```

# Response Example
```
{
    "Action": "CreateURedisGroupResponse", 
    "RetCode": 0, 
    "GroupId": "uredis-00XXX"
}
```

