# 释放 UDPN-ReleaseUDPN

释放 UDPN

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|UDPNId|string|UDPN 资源 Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ReleaseUDPN
&ProjectId=xxxx
&UDPNId=udpn-l5m15x
```

# Response Example
```
{
    "Action": "ReleaseUDPNResponse", 
    "RetCode": 0
}
```

