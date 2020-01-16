# 提交预取任务-PrefetchNewUcdnDomainCache

提交预取任务

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|UrlList.n|string|预热URL列表，n从自然数0开始。|**Yes**|

```
UrlList.n字段必须以”http://域名/”开始。如预取目录a下面img.png文件， 格式为http://abc.ucloud.cn/a/img.png。
不能做目录预取，请正确提交需要刷新的文件URL。

```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TaskId|string|本次提交url对应的任务id|No|

# Request Example
```
https://api.ucloud.cn/?Action=PrefetchNewUcdnDomainCache
&ProjectId=xxxxx
&UrlList.0=http://abc.ucloud.cn/a/1.apk
&UrlList.1=http://abc.ucloud.cn/a/2.apk
```

# Response Example
```
{
    "Action": "PrefetchNewUcdnDomainCacheResponse", 
    "RetCode": 0, 
    "TaskId": "IhrznXRB"
}
```

