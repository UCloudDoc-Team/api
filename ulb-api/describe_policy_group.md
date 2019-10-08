# 获取内容转发组信息-DescribePolicyGroup

获取内容转发组详细信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|GroupId|string|内容转发策略组ID|No|
|Offset|int|数据偏移量，默认值为0|No|
|Limit|int|数据分页值，默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|内容转发策略组列表，具体结构见 UlbPolicyGroupSet|No|

## UlbPolicyGroupSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|GroupId|string|内容转发策略组ID|No|
|GroupName|string|内容转发策略组名称|No|
|PolicySet|array|内容转发策略组详细信息，具体结构见 UlbPolicySet|No|

## UlbPolicySet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|PolicyId|string|内容转发策略组ID|No|
|Type|string|内容转发匹配字段的类型，当前只支持按域名转发。枚举值为： Domain，按域名转发|No|
|Match|string|内容转发匹配字段|No|
|VServerId|string|内容转发策略组ID应用的VServer实例的ID|No|
|BackendSet|array|内容转发策略组ID所应用的后端资源列表，具体结构见 UlbPolicyBackendSet|No|

## UlbPolicyBackendSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BackendId|string|后端资源实例的ID|No|
|PrivateIP|string|后端资源实例的内网IP|No|
|Port|int|后端资源实例的服务端口|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribePolicyGroup
```

# Response Example
```
{
    "Action": "DescribePolicyGroupResponse", 
    "TotalCount": 2, 
    "RetCode": 0, 
    "DataSet": [
        {
            "GroupName": "new-policy", 
            "GroupId": "ulb-fr-2axjbg", 
            "PolicySet": [
                {
                    "VServerId": "8aae44ba-f3fd-4162-9e32-2e64b89b646b", 
                    "BackendSet": [
                        {
                            "Port": 80, 
                            "BackendId": "1cf3c062-f551-48c7-a6e2-c2730d84303f", 
                            "PrivateIP": "10.10.33.87"
                        }, 
                        {
                            "Port": 80, 
                            "BackendId": "a2ac0c73-1831-4379-b651-fbcb7702f6ec", 
                            "PrivateIP": "10.10.32.101"
                        }, 
                        {
                            "Port": 80, 
                            "BackendId": "6277e964-83de-4548-b598-6b4d5a67a442", 
                            "PrivateIP": "10.10.31.7"
                        }
                    ], 
                    "Type": "Domain", 
                    "PolicyId": "a3bfefc1-bfce-459c-baeb-2619f77cf0df", 
                    "Match": "www.example.com"
                }
            ]
        }, 
        {
            "GroupName": "eqeqeqeq", 
            "GroupId": "ulb-fr-dwkb5d", 
            "PolicySet": []
        }
    ]
}
```

