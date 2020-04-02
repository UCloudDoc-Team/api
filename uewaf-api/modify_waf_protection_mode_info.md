# 更改waf工作模式-ModifyWafProtectionModeInfo

更改waf工作模式

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|WorkMode|string|工作模式，Defence:启用防护规则,Alarm:记录不拦截,Inactive:放行|**Yes**|
|FullDomain|string|要变更工作模式的域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyWafProtectionModeInfo
&ProjectId=MGgTQgQh
&WorkMode=Defence
&FullDomain=LsFJkxQS
```

# Response Example
```
{
    "Action": "ModifyWafProtectionModeInfoResponse", 
    "RetCode": 0
}
```

