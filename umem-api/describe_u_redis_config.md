# 查询主备Redis所有配置文件-DescribeURedisConfig

查询主备Redis所有配置文件

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|RegionFlag|bool|是否是跨机房URedis(默认false)|**Yes**|
|Version|string|Redis版本号|No|
|ConfigId|string|配置文件ID|No|
|Offset|int|页显示的起始偏移, 默认值为0|No|
|Limit|int|页显示的条目数, 默认值为10|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|根据过滤条件得到的总数|No|
|DataSet|array|配置文件列表 参见 URedisConfigSet|No|

## URedisConfigSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|Zone|No|
|ConfigId|string|配置ID|No|
|Name|string|配置名称|No|
|Description|string|配置描述|No|
|Version|string|配置对应的Redis版本|No|
|IsModify|string|置是否可以修改|No|
|State|string|配置所处的状态|No|
|CreateTime|int|创建时间 (UNIX时间戳)|No|
|ModifyTime|int|修改时间 (UNIX时间戳)|No|
|RegionFlag|bool|是否是跨机房URedis(默认false)|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeURedisConfig
&Region=cn-zj
&Zone=cn-zj-01
&ConfigId=EmTNpurL
&Offset=8
&Limit=2
&ProjectId=VuPSDiad
&Version=qyhfGmaZ
```

# Response Example
```
{
    "Action": "DescribeURedisConfigResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "Name": "redis-3.0", 
            "Zone": "......", 
            "RegionFlag": false, 
            "State": "Usable", 
            "Version": "3.0", 
            "ModifyTime": 1425458755, 
            "ConfigId": "03f58ca9-b64d-4bdd-abc7-c6b9a46fd801", 
            "IsModify": "Unmodifiable", 
            "CreateTime": 1425458755, 
            "Description": "default-config"
        }
    ]
}
```

