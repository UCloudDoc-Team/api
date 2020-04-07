# 删除WAF防御域名-DeleteWafDomainHostInfo

删除WAF防御域名

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要删除的域名，该字段与RecordId不能同时为空，优先取RecordId进行删除|No|
|RecordId|int|要删除的域名记录ID，该字段与FullDomain不能同时为空，优先取RecordId进行删除|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteWafDomainHostInfo
&ProjectId=org-xxx
&FullDomain=www.test.com
```

# Response Example
```
{
    "Action": "DeleteWafDomainHostInfoResponse", 
    "RetCode": 0
}
```

