# 创建加速实例转发器-CreateUGAForwarder

创建加速实例转发器，  支持HTTPS接入HTTPS回源、HTTPS接入HTTP回源、HTTP接入HTTP回源、TCP接入TCP回源、UDP接入UDP回源

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UGAId|string|加速配置实例ID|**Yes**|
|HTTPHTTP.n|int|HTTP接入HTTP回源转发，接入端口。禁用65123端口|No|
|HTTPHTTPRS.n|int|HTTP接入HTTP回源转发，源站监听端口|No|
|HTTPSHTTP.n|int|HTTPS接入HTTP回源转发，接入端口。禁用65123端口|No|
|HTTPSHTTPRS.n|int|HTTPS接入HTTP回源转发，回源端口|No|
|HTTPSHTTPS.n|int|HTTPS接入HTTPS回源转发，接入端口。禁用65123端口|No|
|HTTPSHTTPSRS.n|int|HTTPS接入HTTPS回源转发，源站监听端口|No|
|TCP.n|int|TCP接入端口|No|
|TCPRS.n|int|TCP回源端口|No|
|UDP.n|int|UDP接入端口|No|
|UDPRS.n|int|UDP回源端口|No|

?> 目前UGA同时支持4层和7层接入端口 使用相同的加速域名接入。因此TCP协议 接入端口与HTTP(s)类协议接入端口不能相同；如果需要从TCP加速转为HTTP加速，请先使用DeleteUGAForwarder接口删除已经存在的TCP端口加速 再使用CreateUGAForwarder增加HTTP加速端口；修改回源端口也需要删除现有的端口加速再添加新的

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回信息 说明|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUGAForwarder
&ProjectId=org-xxxx
&UGAId=uga-xxxx
&HTTPHTTP.n=80
&HTTPHTTPRS.n=80
&HTTPSHTTP.n=443
&HTTPSHTTPRS.n=80
&TCP.n=22
&TCPRS.n=22
```

# Response Example
```
{
    "Action": "CreateUGAForwarderResponse", 
    "Message": "", 
    "RetCode": 0
}
```

