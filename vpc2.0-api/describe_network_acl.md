# 获取网络ACL-DescribeNetworkAcl

获取网络ACL

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Offset|int|列表偏移量|No|
|Limit|string|列表获取的个数限制|No|
|VpcId|string|需要获取的ACL所属的VPC的ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|AclList|array|ACL的信息，具体结构见下方AclInfo|**Yes**|

## AclInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|VpcId|string|ACL所属的VPC ID|**Yes**|
|AclId|string|ACL的ID|**Yes**|
|AclName|string|名称|**Yes**|
|Description|string|描述|**Yes**|
|Entries|array|所有的规则|**Yes**|
|Associations|array|所有的绑定关系，具体结构见下方AssociationInfo|**Yes**|
|CreateTime|int|创建的Unix时间戳|**Yes**|
|UpdateTime|int|更改的Unix时间戳|**Yes**|

## AclEntryInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|EntryId|string|Entry的ID|**Yes**|
|Priority|string|优先级|**Yes**|
|Direction|string|出向或者入向|**Yes**|
|IpProtocol|string|针对的IP协议|**Yes**|
|CidrBlock|string|IP段的CIDR信息|**Yes**|
|PortRange|string|Port的段信息|**Yes**|
|EntryAction|string|匹配规则的动作|**Yes**|
|TargetType|int|应用目标类型。 0代表“子网内全部资源” ，1代表“子网内指定资源” 。|**Yes**|
|CreateTime|int|创建的Unix时间戳|**Yes**|
|UpdateTime|int|更改的Unix时间戳|**Yes**|
|TargetResourceList|array|应用目标资源信息。TargetType为0时不返回该值。具体结构见下方TargetResourceInfo|No|
|TargetResourceCount|int|应用目标资源数量。TargetType为0时不返回该值。|No|

## AssociationInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AssociationId|string|绑定ID|**Yes**|
|VpcId|string|所属的VPC ID|**Yes**|
|AclId|string|ACL的ID|**Yes**|
|SubnetworkId|string|绑定的子网ID|**Yes**|
|CreateTime|int|创建的Unix时间戳|**Yes**|

## TargetResourceInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SubnetworkId|string|子网ID|**Yes**|
|ResourceName|string|资源名称|**Yes**|
|ResourceId|string|资源ID|**Yes**|
|ResourceType|int|资源类型|**Yes**|
|SubResourceName|string|资源绑定的虚拟网卡的名称|**Yes**|
|SubResourceId|string|资源绑定的虚拟网卡的ID|**Yes**|
|SubResourceType|int|资源绑定虚拟网卡的类型|**Yes**|
|PrivateIP|string|资源内网IP|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeNetworkAcl
&Region=cn-bj
&ProjectId=org-xxxxx
&VpcId=uvnet-xxxxxx
&Offset=2
&Limit=vTnIQqcI
```

# Response Example
```
{
    "Action": "DescribeNetworkAclResponse", 
    "TotalCount": 2, 
    "AclList": [
        {
            "Associations": [
                {
                    "AssociationId": "netaclassoc_xxxxxx", 
                    "SubnetworkId": "subnet-xxxxxx", 
                    "CreateTime": 2, 
                    "AclId": "netacl-xxxxxx"
                }
            ], 
            "UpdateTime": 5, 
            "VpcId": "uvnet-xxxxxx", 
            "Description": "", 
            "AclId": "netacl-xxxxxx", 
            "AclName": "sdfsdfsdf", 
            "Entries": [
                {
                    "TargetType": 0, 
                    "Direction": "Ingress", 
                    "Description": "sdsdsd", 
                    "PortRange": "All", 
                    "UpdateTime": 8, 
                    "Priority": "100", 
                    "TargetResourceCount": 0, 
                    "EntryId": "netaclentry_xxxxxx", 
                    "EntryAction": "Accept", 
                    "IpProtocol": "TCP", 
                    "CidrBlock": "0.0.0.0/0", 
                    "CreateTime": 1, 
                    "TargetResourceList": null
                }, 
                {
                    "TargetType": 0, 
                    "Direction": "Egress", 
                    "Description": "sdsdsfd", 
                    "PortRange": "All", 
                    "UpdateTime": 2, 
                    "Priority": "1000", 
                    "TargetResourceCount": 0, 
                    "EntryId": "netaclentry_xxxxxx", 
                    "EntryAction": "Accept", 
                    "IpProtocol": "TCP", 
                    "CidrBlock": "0.0.0.0/0", 
                    "CreateTime": 3, 
                    "TargetResourceList": null
                }
            ], 
            "CreateTime": 4
        }, 
        {
            "Associations": null, 
            "UpdateTime": 3, 
            "VpcId": "uvnet-xxxxxx", 
            "Description": "BVJDOIFdkf", 
            "AclId": "netacl-xxxxxx", 
            "AclName": "DKLGHDhfdj", 
            "Entries": [
                {
                    "TargetType": 0, 
                    "Direction": "Egress", 
                    "Description": "vdfdgg", 
                    "PortRange": "All", 
                    "UpdateTime": 7, 
                    "Priority": "100", 
                    "TargetResourceCount": 0, 
                    "EntryId": "netaclentry_xxxxxx", 
                    "EntryAction": "Reject", 
                    "IpProtocol": "TCP", 
                    "CidrBlock": "10.10.10.10/32", 
                    "CreateTime": 4, 
                    "TargetResourceList": null
                }, 
                {
                    "TargetType": 0, 
                    "Direction": "Ingress", 
                    "Description": "uykj", 
                    "PortRange": "All", 
                    "UpdateTime": 9, 
                    "Priority": "1000", 
                    "TargetResourceCount": 0, 
                    "EntryId": "netaclentry_xxxxxx", 
                    "EntryAction": "Reject", 
                    "IpProtocol": "TCP", 
                    "CidrBlock": "10.10.10.10/32", 
                    "CreateTime": 6, 
                    "TargetResourceList": null
                }
            ], 
            "CreateTime": 1
        }
    ], 
    "RetCode": 0
}
```

