# 创建网络ACL-CreateNetworkAcl

创建网络ACL

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|VpcId|string|将要创建的ACL所属VPC的ID|**Yes**|
|AclName|string|ACL的名称|**Yes**|
|Description|string|ACL的描述|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|AclId|string|创建的ACL的ID|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateNetworkAcl
&VpcId=uvnet-xxxxxx
&AclName=CSMmTACF
&Description=YDdjjiUK
&Region=cn-bj
&ProjectId=org-xxxxx
```

# Response Example
```
{
    "Action": "CreateNetworkAclResponse", 
    "RetCode": 0, 
    "AclId": "netacl-xxxxxx"
}
```

