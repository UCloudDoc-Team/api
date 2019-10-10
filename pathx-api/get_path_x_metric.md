# 获取全球加速监控信息-GetPathXMetric

获取全球加速监控信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|ResourceId|string|ResourceId，如upath ID  和 uga ID |**Yes**|
|BeginTime|int|查询起始时间|**Yes**|
|EndTime|int|查询结束时间|**Yes**|
|MetricName.n|string|查询的监控项，以逗号分隔，拼接成一个字符串。目前仅允许一下内容：NetworkOut:出口带宽，NetworkIn:入口带宽，NetworkOutUsage:出口使用率，NetworkInUsage:入口使用率，TCPDelay:tcp延迟,InputRetransmitRate：输入重传率，OutputRetransmitRate：输出重传率；TCPConNum：tcp连接数|**Yes**|
|ResourceType|string|upath:加速线路,uga:加速实例|**Yes**|
|LineId|string|具体线路id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array||No|

## MetricPeriod
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DiskUsage|array|磁盘利用率|No|
|CPUUtilization|array|CPU使用率|No|
|MemUsage|array|内存使用率|No|
|ConnectionCount|array|TCP连接数|No|
|QPS|array|QPS 次/秒|No|
|SandboxMemory|array|DB系统内存使用量|No|

## MetricPoint
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Value|int||**Yes**|
|Timestamp|int||**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetPathXMetric
&ResourceId=dGHmatXP
&BeginTime=8
&EndTime=7
&MetricName=geZTmWNK
&ResourceType=upath
&LineId=mRaKrOqb
```

# Response Example
```
{
    "Action": "GetPathXMetricResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "ConnectionCount": [
                {
                    "Timestamp": 9, 
                    "Value": 9
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 3, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 4, 
                    "Value": 1
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 4
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 3
                }
            ], 
            "MemUsage": [
                {
                    "Timestamp": 9, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 8, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 3
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 9
                }, 
                {
                    "Timestamp": 7, 
                    "Value": 3
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 9
                }, 
                {
                    "Timestamp": 4, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 8, 
                    "Value": 4
                }
            ], 
            "SandboxMemory": [
                {
                    "Timestamp": 1, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 4
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 9, 
                    "Value": 4
                }, 
                {
                    "Timestamp": 3, 
                    "Value": 2
                }
            ], 
            "QPS": [
                {
                    "Timestamp": 1, 
                    "Value": 5
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 3
                }, 
                {
                    "Timestamp": 3, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 3, 
                    "Value": 1
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 7
                }
            ], 
            "DiskUsage": [
                {
                    "Timestamp": 1, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 3
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 5
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 7
                }
            ], 
            "CPUUtilization": [
                {
                    "Timestamp": 3, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 5
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 1
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 4, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 7, 
                    "Value": 1
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 7
                }
            ]
        }, 
        {
            "ConnectionCount": [
                {
                    "Timestamp": 2, 
                    "Value": 1
                }, 
                {
                    "Timestamp": 7, 
                    "Value": 5
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 9, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 8, 
                    "Value": 2
                }
            ], 
            "MemUsage": [
                {
                    "Timestamp": 9, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 3
                }, 
                {
                    "Timestamp": 9, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 7, 
                    "Value": 4
                }, 
                {
                    "Timestamp": 4, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 5
                }, 
                {
                    "Timestamp": 9, 
                    "Value": 9
                }, 
                {
                    "Timestamp": 3, 
                    "Value": 6
                }
            ], 
            "SandboxMemory": [
                {
                    "Timestamp": 6, 
                    "Value": 1
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 9, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 5
                }, 
                {
                    "Timestamp": 3, 
                    "Value": 3
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 5
                }
            ], 
            "QPS": [
                {
                    "Timestamp": 4, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 1
                }
            ], 
            "DiskUsage": [
                {
                    "Timestamp": 2, 
                    "Value": 9
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 6
                }
            ], 
            "CPUUtilization": [
                {
                    "Timestamp": 7, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 9
                }, 
                {
                    "Timestamp": 3, 
                    "Value": 4
                }, 
                {
                    "Timestamp": 7, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 5
                }, 
                {
                    "Timestamp": 9, 
                    "Value": 9
                }, 
                {
                    "Timestamp": 7, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 6, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 4, 
                    "Value": 2
                }
            ]
        }, 
        {
            "ConnectionCount": [
                {
                    "Timestamp": 5, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 7, 
                    "Value": 7
                }
            ], 
            "MemUsage": [
                {
                    "Timestamp": 3, 
                    "Value": 1
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 5
                }, 
                {
                    "Timestamp": 3, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 8, 
                    "Value": 2
                }, 
                {
                    "Timestamp": 8, 
                    "Value": 3
                }, 
                {
                    "Timestamp": 9, 
                    "Value": 5
                }, 
                {
                    "Timestamp": 7, 
                    "Value": 3
                }
            ], 
            "SandboxMemory": [
                {
                    "Timestamp": 1, 
                    "Value": 9
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 4, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 4
                }
            ], 
            "QPS": [
                {
                    "Timestamp": 1, 
                    "Value": 9
                }, 
                {
                    "Timestamp": 4, 
                    "Value": 5
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 3
                }, 
                {
                    "Timestamp": 9, 
                    "Value": 2
                }
            ], 
            "DiskUsage": [
                {
                    "Timestamp": 2, 
                    "Value": 5
                }, 
                {
                    "Timestamp": 5, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 3, 
                    "Value": 9
                }
            ], 
            "CPUUtilization": [
                {
                    "Timestamp": 1, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 3, 
                    "Value": 3
                }, 
                {
                    "Timestamp": 4, 
                    "Value": 8
                }, 
                {
                    "Timestamp": 1, 
                    "Value": 1
                }, 
                {
                    "Timestamp": 2, 
                    "Value": 1
                }, 
                {
                    "Timestamp": 4, 
                    "Value": 7
                }, 
                {
                    "Timestamp": 8, 
                    "Value": 3
                }, 
                {
                    "Timestamp": 7, 
                    "Value": 6
                }, 
                {
                    "Timestamp": 9, 
                    "Value": 3
                }, 
                {
                    "Timestamp": 4, 
                    "Value": 7
                }
            ]
        }
    ]
}
```

