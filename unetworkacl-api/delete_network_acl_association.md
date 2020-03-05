# 删除网络ACL绑定关系-DeleteNetworkAclAssociation

删除网络ACL绑定关系

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|AclId|string|需要删除的AclId|**Yes**|
|SubnetworkId|string|绑定的子网ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteNetworkAclAssociation
&Region=cn-bj
&ProjectId=org-xxxxx
&SubnetworkId=subnet-xxxxxx
&AclId=netacl-xxxxxx
```

# Response Example
```
{
    "Action": "DeleteNetworkAclAssociationResponse", 
    "RetCode": 0
}
```

