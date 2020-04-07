# 删除域名白名单记录-DeleteWafDomainWhiteList

删除域名白名单记录

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|域名|**Yes**|
|ID|int|白名单记录ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteWafDomainWhiteList
&ProjectId=org-xxx
&FullDomain=www.test.com
&ID=7
```

# Response Example
```
{
    "Action": "DeleteWafDomainWhiteListResponse", 
    "RetCode": 0
}
```

