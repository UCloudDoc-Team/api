# 刷新缓存-RefreshNewUcdnDomainCache

刷新缓存

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Type|string|刷新类型，file代表文件刷新，dir 代表路径刷新|**Yes**|
|UrlList.n|string|刷新多个URL列表时，一次最多提交30个。必须以”http://域名/”开始。目录要以”/”结尾， 如刷新目录a下所有文件，格式为：http://abc.ucloud.cn/a/；如刷新文件目录a下面img.png文件， 格式为http://abc.ucloud.cn/a/img.png。请正确提交需要刷新的域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TaskId|string|本次提交url对应的任务id|No|

# Request Example
```
https://api.ucloud.cn/?Action=RefreshNewUcdnDomainCache
&ProjectId=xxxx
&Type=QPmGdEvf
&UrlList.0=http://abc.ucloud.cn/a/img.png
&UrlList.1=http://abc.ucloud.cn/a/img1.png
```

# Response Example
```
{
    "Action": "RefreshNewUcdnDomainCacheResponse", 
    "RetCode": 0, 
    "TaskId": "kRtSCEHO"
}
```

