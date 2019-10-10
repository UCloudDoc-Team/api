# 查看配额使用报表-GetUFileReport

查看配额使用报表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|StartTime|int|查询开始时间|**Yes**|
|EndTime|int|查询结束时间|**Yes**|

```
说明：1. 参数EntTime和StartTime都是unix时间戳，必须保证 EndTime < StartTime，并且时间差小于一年。
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|报表内容 参数见 UFileReportSet|No|

## UFileReportSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Time|int|配额消费时间，unix时间戳，精确到日期|No|
|StorageVolume|float|配额消费当日使用的存储容量，单位：GB*天|No|
|DownloadTraffic|float|配额消费当日使用的下载流量，单位：GB|No|
|RequestCount|float|配额消费当日使用的请求次数，单位：万次|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUFileReport
&Region=cn-bj2
&StartTime=1427558400
&EndTime=1427644799
```

# Response Example
```
{
    "Action": "GetUFileReportResponse", 
    "Retcode": 0, 
    "DataSet": [
        {
            "DownloadTraffic": 10, 
            "StorageVolume": 32, 
            "RequestCount": 10343, 
            "Time": 1427558400
        }
    ]
}
```

