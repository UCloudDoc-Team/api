# 获取清洗流量历史统计-GetCleanServiceStatistics

获取清洗流量历史统计

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceId|string|资源id,不允许为空|**Yes**|
|BeginTime|string|查询开始时间|**Yes**|
|EndTime|string|查询结束时间|**Yes**|
|DefenceIP|string|当DefenceIP为空时，接口返回资源所处区域内被攻击流量最大的5个IP;当DefenceIP为某一IP时，接口返回资源所处区域内该IP的清洗前后流量数据;|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DefenceIPList|array|当DefenceIP为空时，仅返回TOP 5 流量的IP数组列表|**Yes**|
|CleanStatistics|string|当DefenceIP表示单个IP时，仅返回此项。代表指定时间内该IP的PPS和BPS等信息|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetCleanServiceStatistics
&ResourceId=usecure_UCLEAN-2cy3wd
&top_organization_id=200000103
&organization_id=200000217
&account_id=200000103
&BeginTime=1523089529
&EndTime=1593089529
&DefenceIP=120.132.20.20

```

# Response Example
```
{
    "Action": "GetCleanServiceStatisticsResponse", 
    "RetCode": 0, 
    "DefenceIPList": [
        "106.75.145.36", 
        "106.75.175.222", 
        "106.75.49.5", 
        "120.132.20.20"
    ]
}
```

