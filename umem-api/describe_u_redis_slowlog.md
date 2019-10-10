# 查询URedis慢日志-DescribeURedisSlowlog

查询URedis慢日志

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|GroupId|string|资源ID|**Yes**|
|Limit|int|分页显示的条目数，默认为10|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|总条目数|**Yes**|
|DataSet|array|条目数据|No|

## URedisSlowlogSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|StartTime|int|查询发生的时间|No|
|SpendTime|int|查询消耗的时间|No|
|Command|string|查询命令|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeURedisSlowlog
&Region=iBpXSJCs
&GroupId=GrhAxSKP
&Limit=3
&ProjectId=LnUyjCiS
```

# Response Example
```
{
    "Action": "DescribeURedisSlowlogResponse", 
    "TotalCount": 3, 
    "RetCode": 0, 
    "DataSet": [
        {
            "SpendTime": 3180000, 
            "Command": "XXXX ", 
            "StartTime": 1560000000
        }, 
        {
            "SpendTime": 3180000, 
            "Command": "XXXX ", 
            "StartTime": 1560000000
        }, 
        {
            "SpendTime": 3180000, 
            "Command": "XXXX ", 
            "StartTime": 1560000000
        }
    ]
}
```

