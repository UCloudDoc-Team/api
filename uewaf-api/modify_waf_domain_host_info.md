# 编辑防护域名信息-ModifyWafDomainHostInfo

编辑防护域名信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SrcIP.n|string|源站IP信息|**Yes**|
|WorkRegions|string|工作区域，用户已购买区域的子集，以逗号分隔，如：cn-bj,cn-sh|**Yes**|
|FullDomain|string|被编辑的域名,域名与记录ID必须选填一项|No|
|RecordId|string|被编辑的域名记录ID，域名与记录ID必须选填一项|No|
|HTTPRedirection|string|使用HTTP跳转，YES是，NO否，只允许HTTPS:YES,HTTP:NO的情况下使用|No|
|CertificateID|int|HTTPS证书编号|No|
|RealIPHeader|string|获取真实客户端地址字段，如对接CDN等其他代理时使用|No|
|WorkMode|string|工作模式，Defence:启用防护规则,Alarm:记录不拦截,Inactive:放行；默认Alarm|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyWafDomainHostInfo
&FullDomain=UXsrGhDX
&SrcIP.n=osaYxWFF
&HTTPRedirection=mYCbrHFD
&WorkRegions=fOGGqJCj
&CertificateID=5
&ProjectId=VROXtRzF
```

# Response Example
```
{
    "Action": "ModifyWafDomainHostInfoResponse", 
    "RetCode": 0
}
```

