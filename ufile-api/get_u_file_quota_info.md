# 获取配额信息-GetUFileQuotaInfo

获取配额信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|QuotaType.n|string|配额类型，取值为storage-volume, download-traffic或request-count|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|配额信息数据集|No|

## UFileQuotaDataSetItem
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|可用地域|No|
|Owe|int|是否欠费：1表示欠费；0表示未欠费|No|
|Storage|float|剩余存储容量|No|
|DownloadFlow|float|剩余下载流量|No|
|RequestCnt|float|剩余请求次数|No|

## UFileQuotaLeft
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Left|float|配额剩余量|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUFileQuotaInfo
&Region=cn-bj2
&QuotaType.0=storage-volume
&QuotaType.1=download-traffic
&QuotaType.2=request-count
&ProjectId=org-5150
```

# Response Example
```
{
    "Action": "GetUFileQuotaInfoResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "Owe": 1, 
            "DownloadFlow": {
                "Left": -5.180299999999999
            }, 
            "Region": "cn-bj", 
            "Storage": {
                "Left": -13507.2
            }, 
            "RequestCnt": {
                "Left": 202
            }
        }
    ]
}
```

