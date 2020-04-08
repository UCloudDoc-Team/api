# 编辑域名白名单-ModifyWafDomainWhiteList

编辑域名白名单

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ID|int|要编辑的白名单记录ID|**Yes**|
|FullDomain|string|该条记录所属的域名|**Yes**|
|CIDRS.n|string|IP、网段或者IP段，传递数组|No|
|Name|string|规则名称|No|
|Remark|string|备注信息|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyWafDomainWhiteList
&ProjectId=org-xxx
&FullDomain=www.test.com
&ID=4
&CIDRS.0=2.2.2.3/31
&RecordId=8
&Remark=test
```

# Response Example
```
{
    "Action": "ModifyWafDomainWhiteListResponse", 
    "RetCode": 0
}
```

