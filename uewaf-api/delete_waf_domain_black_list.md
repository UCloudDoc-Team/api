# 删除域名黑名单记录-DeleteWafDomainBlackList

删除域名黑名单记录

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|域名|**Yes**|
|ID|int|黑名单记录id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteWafDomainBlackList
&ProjectId=org-xxx
&FullDomain=www.test.com
&ID=252731
```

# Response Example
```
{
    "Action": "DeleteWafDomainBlackListResponse", 
    "RetCode": 0
}
```

