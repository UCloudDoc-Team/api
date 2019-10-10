# 删除加速实例转发器-DeleteUGAForwarder

删除加速实例转发器 按接入端口删除

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UGAId|string|UGA 加速实例ID|**Yes**|
|HTTPHTTP.n|int|HTTP接入HTTP回源，接入端口|No|
|HTTPSHTTP.n|int|HTTPS接入HTTP回源， 接入端口|No|
|HTTPSHTTPS.n|int|HTTPS接入HTTPS回源， 接入端口|No|
|TCP.n|int|TCP接入端口|No|
|UDP.n|int|UDP接入端口|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回信息 说明|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUGAForwarder
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=abdOFLDP
&UGAId=GcJttJDc
&HTTPHTTP.n=3
&HTTPSHTTP.n=4
&HTTPSHTTPS.n=7
&TCP.n=5
&UDP.n=5
```

# Response Example
```
{
    "Action": "DeleteUGAForwarderResponse", 
    "Message": "hMorNbjH", 
    "RetCode": 0
}
```

