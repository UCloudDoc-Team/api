# 获取监控概况数据-GetMetricOverview

获取资源当前各项监控指标数据

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID，不填为默认项目。子账户必须填写项目ID|No|
|ResourceType|string|资源类型|**Yes**|
|MetricName.n|string|监控指标名称，若省略则返回所有监控指标数据|No|
|Limit|int|数据分页值，默认为20|No|
|Offset|int|数据偏移量，默认为0|No|

?> 
note
资源类型及监控指标，参见 GetMetric文档



# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|JSON格式监控数据列表|No|
|RefreshTime|int|系统更新时间，格式为Unix Timestamp|No|
|ResourceType|string|资源类型|No|
|TotalCount|int|返回总数量|No|

## ResourceItemSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceId|string|资源ID|No|
|Name|string|资源名称|No|
|MetricName|string|对应监控项的监控数据|No|

# Request Example
```
https://api.ucloud.cn/?action=GetMetricOverview
&Region=cn-bj2
&Zone=cn-bj2-04
&ResourceType=uhost
```

# Response Example
```
{
    "RetCode": 0, 
    "ResourceType": "uhost", 
    "RefreshTime": 1431507033, 
    "DataSet": [
        {
            "NICOut": 3944, 
            "Remark": "", 
            "RunnableProcessCount": 0, 
            "MemUsage": 0, 
            "Name": "testtest", 
            "IORead": 0, 
            "IOWrite": 4641, 
            "ResourceId": "uhost-xxx", 
            "RootSpaceUsage": 0, 
            "NICIn": 3002, 
            "DataSpaceUsage": 0, 
            "BlockProcessCount": 0, 
            "NetPacketOut": 2, 
            "DiskWriteOps": 0, 
            "DiskReadOps": 0, 
            "NetPacketIn": 2, 
            "CPUUtilization": 0, 
            "Uuid": "0e796e5a-e004-42a2-92be-77277bde9144"
        }
    ], 
    "TotalCount": 1, 
    "Action": "GetMetricOverviewResponse"
}
```

