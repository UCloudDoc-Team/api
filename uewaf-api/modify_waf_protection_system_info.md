# 修改用户系统规则-ModifyWafProtectionSystemInfo

修改用户系统规则放行或拦截

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要操作的域名|**Yes**|
|Deny.n|int|设置为拦截的系统默认规则|No|
|Accept.n|int|设置为放行的系统默认规则|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyWafProtectionSystemInfo
&ProjectId=FswqJags
&FullDomain=dnsJDDMZ
&Deny.n=4
&Accept.n=6
```

# Response Example
```
{
    "Action": "ModifyWafProtectionSystemInfoResponse", 
    "RetCode": 0
}
```

