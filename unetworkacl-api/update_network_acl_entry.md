# 更新ACL的规则-UpdateNetworkAclEntry

更新ACL的规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|AclId|string|ACL的ID|**Yes**|
|EntryId|string|需要更新的Entry Id|**Yes**|
|Priority|int|Entry的优先级，对于同样的Direction来说，不能重复|**Yes**|
|Direction|string|出向或者入向（“Ingress”, "Egress")|**Yes**|
|IpProtocol|string|针对的协议规则|**Yes**|
|CidrBlock|string|IPv4段的CIDR表示|**Yes**|
|PortRange|string|针对的端口范围|**Yes**|
|EntryAction|string|规则的行为("Accept", "Reject")|**Yes**|
|Description|string|描述|No|
|TargetType|int|应用目标类型。0代表“子网内全部资源”， 1代表“子网内指定资源”。默认为0|No|
|TargetResourceIds.n|string|应用目标资源列表。默认为全部资源生效。TargetType为0时不用填写该值|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateNetworkAclEntry
&Region=cn-bj
&AclId=netacl-xxxxxx
&EntryId=netaclentry_xxxxxx
&Priority=4
&Direction=Ingress
&IpProtocol=TCP
&CidrBlock=0.0.0.0/0
&PortRange=1-65535
&EntryAction=WefbebUQ
&Description=kazGjdPZ
&TargetType=4
&TargetResourceIds.n=JNflNaTv
```

# Response Example
```
{
    "Action": "UpdateNetworkAclEntryResponse", 
    "RetCode": 0
}
```

