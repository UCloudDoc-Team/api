# 获取子网的ACL绑定信息-DescribeNetworkAclAssociationBySubnet

获取子网的ACL绑定信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SubnetworkId|string|子网的ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Association|object|绑定信息|**Yes**|

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
https://api.ucloud.cn/?Action=DescribeNetworkAclAssociationBySubnet
&Region=cn-bj
&ProjectId=org-xxxxx
&SubnetworkId=subnet-xxxxxx
```

# Response Example
```
{
    "Action": "DescribeNetworkAclAssociationBySubnetResponse", 
    "AssociationList": [
        {
            "AssociationId": "netaclassoc_xxxxxx", 
            "SubnetworkId": "subnet-xxxxxx", 
            "CreateTime": 1, 
            "AclId": "netacl-xxxxxx"
        }, 
        {
            "AssociationId": "netaclassoc_xxxxxx", 
            "SubnetworkId": "subnet-xxxxxx", 
            "CreateTime": 9, 
            "AclId": "netacl-xxxxxx"
        }, 
        {
            "AssociationId": "netaclassoc_xxxxxx", 
            "SubnetworkId": "subnet-xxxxxx", 
            "CreateTime": 9, 
            "AclId": "netacl-xxxxxx"
        }, 
        {
            "AssociationId": "netaclassoc_xxxxxx", 
            "SubnetworkId": "subnet-xxxxxx", 
            "CreateTime": 10, 
            "AclId": "netacl-xxxxxx"
        }
    ], 
    "RetCode": 0
}
```

