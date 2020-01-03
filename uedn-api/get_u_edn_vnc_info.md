# 获取vnc登录信息-GetUEdnVncInfo

获取vnc登录信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NodeId|string|节点ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|NodeId|string|节点ID|**Yes**|
|VncIP|string|Vnc登录IP|**Yes**|
|VncPort|int|Vnc登录端口|**Yes**|
|VncPassword|string|Vnc 登录密码|**Yes**|
|VncToken|string|Vnc token，一次访问有效|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUEdnVncInfo
&ProjectId=VkGeNeZM
&NodeId=Hbvirfhj
```

# Response Example
```
{
    "VncIP": "VZaZkFTg", 
    "VncPassword": "CLIMiIit", 
    "RetCode": 0, 
    "NodeId": "UIASOFRM", 
    "Action": "GetUEdnVncInfoResponse", 
    "VncToken": "kacNlSjP", 
    "VncPort": 3
}
```

