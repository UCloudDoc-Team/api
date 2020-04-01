# 新增防护域名配置-AddWafDomainHostInfo

新增防护域名配置

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要防护的域名|**Yes**|
|WorkRegions|string|工作区域，用户已购买区域的子集，以逗号分隔，如：cn-bj,cn-sh|**Yes**|
|WorkMode|string|工作模式，Defence:启用防护规则,Alarm:记录不拦截,Inactive:放行；默认Alarm|No|
|SrcIP.n|string|源站IP端口信息，格式为：http://192.168.1.1或http://192.168.1.1:80；兼容http:192.168.1.1:80，支持CNAME|No|
|CertificateID|int|HTTPS证书编号，源站前缀为https时必填|No|
|HTTPRedirection|string|使用HTTP跳转，YES是，NO否，只允许HTTPS:YES,HTTP:NO的情况下使用且只配置了https 443端口的源站|No|
|ExclusiveIP|string|标识该域名使用独享防御IP，YES是，NO否；启用将为改域名分配一个独享防御IP|No|
|RealIPHeader|string|获取真实客户端地址字段，如对接CDN等其他代理时使用|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Id|int|添加成功后返回的域名配置ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=AddWafDomainHostInfo
&FullDomain=QLlQQKaC
&SrcIPNum=7
&Http=YES
&Https=YES
&SrcIP.n=vSmWPhJn
&CertificateID=KwsvOdlM
&CertificateID=9
&ExclusiveIP=URsAvOxw
&HTTPRedirection=NZTPNDdo
&WorkRegions=BoPHvCAD
&ProjectId=XOUYQpyF
```

# Response Example
```
{
    "Action": "AddWafDomainHostInfoResponse", 
    "RetCode": 0, 
    "Id": 9
}
```

