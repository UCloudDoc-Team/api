# 创建ACL的绑定关系-CreateNetworkAclAssociation

创建ACL的绑定关系

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|AclId|string|ACL的ID|**Yes**|
|SubnetworkId|string|需要绑定的子网ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|AclId|string|Acl的ID|**Yes**|
|AssociationId|string|创建的绑定关系的ID|**Yes**|
|PrevAssociation|object|该子网之前的绑定关系信息|No|

## AssociationInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AssociationId|string|绑定ID|**Yes**|
|VpcId|string|所属的VPC ID|**Yes**|
|AclId|string|ACL的ID|**Yes**|
|SubnetworkId|string|绑定的子网ID|**Yes**|
|CreateTime|int|创建的Unix时间戳|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateNetworkAclAssociation
&VpcId=uvnet-xxxxxx
&AclId=netacl-xxxxxx
&Region=cn-bj
&ProjectId=org-xxxxx
&SubnetworkId=subnet-xxxxxx
```

# Response Example
```
{
    "Action": "CreateNetworkAclAssociationResponse", 
    "AssociationId": "netaclassoc_xxxxxx", 
    "RetCode": 0, 
    "PrevAssociation": [
        {
            "AssociationId": "netaclassoc_xxxxxx", 
            "SubnetworkId": "subnet-xxxxxx", 
            "CreateTime": 3, 
            "AclId": "netacl-xxxxxx"
        }
    ]
}
```

