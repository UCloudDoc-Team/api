# 获取ACL规则应用目标列表-GetNetworkAclTargetResource

获取ACL规则应用目标列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SubnetworkId.n|string|子网ID。|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TargetResourceList|array|ACL规则应用目标资源列表，具体结构见下方TargetResourceInfo|**Yes**|
|TotalCount|int|ACL规则应用目标资源总数|**Yes**|

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
https://api.ucloud.cn/?Action=GetNetworkAclTargetResource
&Region=cn-bj
&ProjectId=org-xxxxx
&SubnetworkId.n=subnet-xxxxxx
```

# Response Example
```
{
    "Action": "GetNetworkAclTargetResourceResponse", 
    "TotalCount": 2, 
    "RetCode": 0, 
    "TargetResourceList": [
        {
            "SubResourceId": "", 
            "SubResourceType": 0, 
            "SubnetworkId": "subnet-xxxxxx", 
            "ResourceType": 6, 
            "ResourceId": "udb-xxxxxx", 
            "PrivateIp": "10.23.x.x", 
            "SubResourceName": "", 
            "ResourceName": "UDB"
        }, 
        {
            "SubResourceId": "", 
            "SubResourceType": 0, 
            "SubnetworkId": "subnet-xxxxxx", 
            "ResourceType": 6, 
            "ResourceId": "uhost-xxxxxx", 
            "PrivateIp": "10.19.x.x", 
            "SubResourceName": "", 
            "ResourceName": "UHost"
        }, 
        {
            "SubResourceId": "", 
            "SubResourceType": 0, 
            "SubnetworkId": "subnet-xxxxxx", 
            "ResourceType": 6, 
            "ResourceId": "uredis-xxxxxx", 
            "PrivateIp": "10.23.x.x", 
            "SubResourceName": "", 
            "ResourceName": "URedis"
        }, 
        {
            "SubResourceId": "", 
            "SubResourceType": 0, 
            "SubnetworkId": "subnet-xxxxxx", 
            "ResourceType": 6, 
            "ResourceId": "uhadoop-xxxxxx", 
            "PrivateIp": "10.23.x.x", 
            "SubResourceName": "", 
            "ResourceName": "UHadoop"
        }
    ]
}
```

