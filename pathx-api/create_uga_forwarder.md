# 创建加速实例转发器-CreateUGAForwarder

创建加速实例转发器，  支持HTTPS接入HTTPS回源、HTTPS接入HTTP回源、HTTP接入HTTP回源

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|UGAId|string|UGA 加速实例ID|**Yes**|
|HTTPHTTP.n|int|HTTP接入HTTP回源转发，接入端口|No|
|HTTPHTTPRS.n|int|HTTP接入HTTP回源转发，源站监听端口， 默认为接入端口|No|
|HTTPSHTTP.n|int|HTTPS接入HTTP回源转发，接入端口|No|
|HTTPSHTTPRS.n|int|HTTPS接入HTTP回源转发，回源端口， 默认为接入端口|No|
|HTTPSHTTPS.n|int|HTTPS接入HTTPS回源转发，接入端口|No|
|HTTPSHTTPSRS.n|int|HTTPS接入HTTPS回源转发，源站监听端口， 默认为接入端口|No|
|TCP.n|int|TCP接入端口|No|
|TCPRS.n|int|TCP回源端口，默认同TCP接入端口|No|
|UDP.n|int|UDP接入端口|No|
|UDPRS.n|int|UDP回源端口， 默认同UDP接入端口|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回信息 说明|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUGAForwarder
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=wDUTSPJx
&UGAId=cqUKsWtf
&HTTPHTTP.n=7
&HTTPHTTPRS.n=2
&HTTPSHTTP.n=8
&HTTPSHTTPRS.n=1
&HTTPSHTTPS.n=1
&HTTPSHTTPSRS.n=1
&TCP.n=7
&TCPRS.n=8
&UDP.n=6
&UDPRS.n=4
```

# Response Example
```
{
    "Action": "CreateUGAForwarderResponse", 
    "Message": "EELLFnVb", 
    "RetCode": 0
}
```

