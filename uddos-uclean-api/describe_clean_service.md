# 查询清洗服务-DescribeCleanService

查询清洗服务

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceId|string|资源id，为空代表查询用户下所有清洗资源；不为空时代表查询指定资源ID的清洗服务；默认为空|No|
|Offset|int|数据偏移量, 默认为0。供分页显示使用|No|
|Limit|int|返回清洗的最多条目数, 默认为10。供分页显示使用|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|符合条件的条目总数|**Yes**|
|CleanServiceList|array|清洗服务列表|**Yes**|

## CleanServiceList
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceId|string|资源ID|**Yes**|
|CreateTime|string|创建时间 （时间戳）|**Yes**|
|ExpiredTime|string|过期时间（时间戳）|**Yes**|
|CleanRegion|string|地域|**Yes**|
|MaxCleanCapacity|int|流量清洗上限防护流量（单位G），5、10、15、20、25|**Yes**|
|DefenceStatus|string|状态，清洗服务的当前状态当前状态 (清洗中：Cleaning  过期：Expired)|**Yes**|
|StatusRemarks|string|状态的补充说明（正常：Normal 超限：Exceed）|**Yes**|
|ChargeType|string|计费方式（Month:按月，Year:按年）|**Yes**|
|AutoRenewal|int|自动续费1：开启0：关闭|**Yes**|
|DefenseIP|int|最近一次受攻击的IP|**Yes**|
|DefenseTime|string|最近攻击时间，时间戳|**Yes**|
|DefensePeak|float|最近攻击流量峰值|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeCleanService
&Offset=9
&Limit=7
```

# Response Example
```
{
    "Action": "DescribeCleanServiceResponse", 
    "TotalCount": 2, 
    "CleanServiceList": [
        {
            "CleanRegion": "\u4e0a\u6d77", 
            "MaxCleanCapacity": 15, 
            "DefenseIP": "192.168.254.10", 
            "DefenseFlow": 80.344, 
            "ResourceId": "usecure_UCLEAN-dch4di", 
            "DefenceStatus": "Started", 
            "ExpiredTime": 1529116968, 
            "DefenseTime": 1523334896, 
            "ChargeType": "Month", 
            "AutoRenewal": 1, 
            "CreateTime": 1526438569
        }, 
        {
            "CleanRegion": "\u5317\u4eac", 
            "MaxCleanCapacity": 5, 
            "DefenseIP": "192.168.254.10", 
            "DefenseFlow": 80.344, 
            "ResourceId": "usecure_UCLEAN-sei2sx", 
            "DefenceStatus": "Started", 
            "ExpiredTime": 1529116220, 
            "DefenseTime": 1523334896, 
            "ChargeType": "Month", 
            "AutoRenewal": 1, 
            "CreateTime": 1526437820
        }
    ], 
    "RetCode": 0
}
```

