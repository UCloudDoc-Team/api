# 删除加速实例转发器-DeleteUGAForwarder

删除加速实例转发器 按接入端口删除

!> 删除端口转发器会导致服务立刻失效 请谨慎操作。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UGAId|string|加速配置实例ID|**Yes**|
|HTTPHTTP.n|int|HTTP接入HTTP回源，接入端口。禁用65123端口|No|
|HTTPSHTTP.n|int|HTTPS接入HTTP回源， 接入端口。禁用65123端口|No|
|HTTPSHTTPS.n|int|HTTPS接入HTTPS回源， 接入端口。禁用65123端口|No|
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
&ProjectId=org-xxxx
&UGAId=uga-xxxx
&HTTPHTTP.n=80
&HTTPSHTTP.n=443
&TCP.n=22
```

# Response Example
```
{
    "Action": "DeleteUGAForwarderResponse", 
    "Message": "", 
    "RetCode": 0
}
```

