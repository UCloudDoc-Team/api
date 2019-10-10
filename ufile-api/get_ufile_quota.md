# 查看配额状态-GetUFileQuota

查看配额状态

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|QuotaType|string|配额类型，取值为storage-volume, download-traffic或request-count|**Yes**|

```
该API无法展示地域信息，获取地域配额信息请使用GetUFileQuotaInfo
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|LeftQuota|float|剩余的配额数值|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUFileQuota
&QuotaType=storage-volume
```

# Response Example
```
{
    "Action": "GetUFileQuotaResponse", 
    "LeftQuota": 55, 
    "Retcode": 0
}
```

