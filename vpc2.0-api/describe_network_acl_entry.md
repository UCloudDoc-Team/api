# 获取ACL的规则信息-DescribeNetworkAclEntry

获取ACL的规则信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|AclId|string|ACL的ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|EntryList|array|所有的规则信息|**Yes**|

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

## TargetResourceInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SubnetworkId|string|子网ID|**Yes**|
|ResourceName|string|资源名称|**Yes**|
|ResourceId|string|资源ID|**Yes**|
|ResourceType|int|资源类型|**Yes**|
|SubResourceName|string|资源绑定的虚拟网卡的名称|**Yes**|
|SubResourceId|string|资源绑定的虚拟网卡的ID|**Yes**|
|SubResourceType|string|资源绑定虚拟网卡的类型。uni，“虚拟网卡”。|**Yes**|
|PrivateIP|string|资源内网IP|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeNetworkAclEntry
&Region=cn-bj
&ProjectId=org-xxxxx
&AclId=netacl-xxxxxx
```

# Response Example
```
{
    "Action": "DescribeNetworkAclEntryResponse", 
    "RetCode": 0, 
    "EntryList": [
        {
            "TargetType": 0, 
            "Direction": "Ingress", 
            "Description": "hgrDEGHjv", 
            "PortRange": "All", 
            "UpdateTime": 4, 
            "Priority": "100", 
            "TargetResourceCount": 0, 
            "EntryId": "netaclentry_xxxxx", 
            "IpProtocol": "TCP", 
            "EntryAction": "Accept", 
            "CidrBlock": "0.0.0.0/0", 
            "CreateTime": 9, 
            "TargetResourceList": null
        }, 
        {
            "TargetType": 0, 
            "Direction": "Ingress", 
            "Description": "hgrDEGHjv", 
            "PortRange": "All", 
            "UpdateTime": 4, 
            "Priority": "100", 
            "TargetResourceCount": 0, 
            "EntryId": "netaclentry_xxxxx", 
            "IpProtocol": "TCP", 
            "EntryAction": "Accept", 
            "CidrBlock": "0.0.0.0/0", 
            "CreateTime": 9, 
            "TargetResourceList": null
        }, 
        {
            "TargetType": 0, 
            "Direction": "Egress", 
            "Description": "hgrDEGHjv", 
            "PortRange": "All", 
            "UpdateTime": 4, 
            "Priority": "1000", 
            "TargetResourceCount": 0, 
            "EntryId": "netaclentry_xxxxx", 
            "IpProtocol": "TCP", 
            "EntryAction": "Accept", 
            "CidrBlock": "0.0.0.0/0", 
            "CreateTime": 9, 
            "TargetResourceList": null
        }, 
        {
            "TargetType": 0, 
            "Direction": "Egress", 
            "Description": "hgrDEGHjv", 
            "PortRange": "All", 
            "UpdateTime": 4, 
            "Priority": "1000", 
            "TargetResourceCount": 0, 
            "EntryId": "netaclentry_xxxxx", 
            "IpProtocol": "TCP", 
            "EntryAction": "Accept", 
            "CidrBlock": "0.0.0.0/0", 
            "CreateTime": 9, 
            "TargetResourceList": null
        }
    ]
}
```

