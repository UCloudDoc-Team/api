# 下载访问日志-DownloadWAFAccessLog

下载访问日志

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要下载日志的域名|**Yes**|
|Date|string|日期，yyyy-mm-dd形式|**Yes**|
|LogType|string|accessLog 访问日志，attackLog 攻击日志|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|URL|array|文件下载的URL 列表，每小时提供一个文件|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DownloadWAFAccessLog
&FullDomain=dGMfjoCo
&Date=2
&ProjectId=enHqAeJK
&LogType=XHcQctYV
```

# Response Example
```
{
    "URL": "pboNfIYf", 
    "Action": "DownloadWAFAccessLogResponse", 
    "RetCode": 0
}
```

