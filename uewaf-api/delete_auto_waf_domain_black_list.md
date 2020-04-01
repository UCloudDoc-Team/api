# 删除自动添加黑名单-DeleteAutoWafDomainBlackList

删除自动添加黑名单记录

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要删除的规则所属域名|**Yes**|
|ID|int|要删除的自动拦截规则的ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteAutoWafDomainBlackList
&FullDomain=ejVyvzIt
&ID=6
&ProjectId=lGPOptds
```

# Response Example
```
{
    "Action": "DeleteAutoWafDomainBlackListResponse", 
    "RetCode": 0
}
```

