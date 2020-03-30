# 查看服务状态-GetUDTSTaskStatus

查看服务状态

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|TaskId|string|任务ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Data|object|StatusData|No|
|Message|string|返回信息|No|

## StatusData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|MaxRetryCount|int|用户设置的最大失败重试次数|No|
|Status|string|任务状态, 可能的状态有Checking, Dumping, Loading, Syncing, Done, Failed 等|No|
|FailedMessage|string|当Status为Failed时, 显示失败原因|No|
|CurRetryCount|int|当前失败重试次数|No|
|Progress|object|Progress 全量迁移进度信息， 当类型为增量迁移时为空|No|
|Sync|object|Binlog 信息|No|

## Progress
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TotalCount|int|总条目数|No|
|CurCount|int|已迁移条目数|No|
|TotalDuration|int|估算总耗时间（单位秒）|No|
|CurDuration|int|已耗时间（单位秒）|No|
|Percentage|float|完成进度|No|

## SyncData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BinlogName|string|Binlog 文件名， 长度不超过128字符|**Yes**|
|BinlogPos|int|Binlog Pos|**Yes**|
|ServerId|int|分配给UDTS task的server ID, 必须在MySQL集群中唯一|**Yes**|
|BinlogGTID|string|GTID|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUDTSTaskStatus
&ProjectId=org-hiny12
&TaskId=udts-ixdp441
```

# Response Example
```
{
    "Action": "GetUDTSTaskStatusResponse", 
    "Message": "", 
    "Data": {
        "CurRetryCount": 0, 
        "Status": "Done", 
        "MaxRetryCount": 0, 
        "Sync": {
            "BinlogName": "mysql-bin.000006", 
            "BinlogPos": 154
        }, 
        "Progress": {
            "CurDuration": 0, 
            "TotalCount": 0, 
            "Percentage": 0, 
            "CurCount": 0, 
            "TotalDuration": 0
        }
    }, 
    "RetCode": 0
}
```

