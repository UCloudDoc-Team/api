# 删除waf防御域名-DeleteWafDomainHostInfo

删除waf防御域名

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要删除的域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteWafDomainHostInfo
&ProjectId=reKGgRhH
&FullDomain=zAMzzFba
```

# Response Example
```
{
    "Action": "DeleteWafDomainHostInfoResponse", 
    "RetCode": 0
}
```

