# 设置NAT网关的默认出口-SetGwDefaultExport

设置NAT网关的默认出口

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NATGWId|string|NAT网关Id|**Yes**|
|ExportIp|string|NAT网关绑定的EIP。ExportIp和ExportEipId必填一个|No|
|ExportEipId|string|NAT网关绑定的EIP Id。ExportIp和ExportEipId必填一个|No|

```
ExportIp和ExportEipId必填一个
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=SetGwDefaultExport
&Region=xxx
&ProjectId=xxx
&NATGWId=qqgPfeLU
&ExportIp=PQiJgHRY
```

# Response Example
```
{
    "Action": "SetGwDefaultExportResponse", 
    "RetCode": 0
}
```

