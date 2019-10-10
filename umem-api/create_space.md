# 创建内存空间-CreateUMemSpace

创建UMem内存空间

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Size|int|内存大小, 单位:GB, 范围[1~1024]|**Yes**|
|Name|string|空间名称,长度(6<=size<=63)|**Yes**|
|Protocol|string|协议:memcache, redis (默认redis).注意:redis无single类型|No|
|Type|string|空间类型:single(无热备),double(热备)(默认: double)|No|
|ChargeType|string|Year , Month, Dynamic, Trial 默认: Month|No|
|Quantity|int|购买时长 默认: 1|No|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|SpaceId|string|创建内存空间ID列表|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUMemSpace
&Region=cn-north-02
&Zone=cn-bj2-04
&Size=1
&Name=SpaceName
```

# Response Example
```
{
    "Action": "CreateUMemSpaceResponse", 
    "RetCode": 0, 
    "SpaceId": "umem-opqmjd"
}
```

