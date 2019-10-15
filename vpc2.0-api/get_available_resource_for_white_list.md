# 获取NAT网关可添加白名单的资源-GetAvailableResourceForWhiteList

获取NAT网关可添加白名单的资源

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NATGWId|string|NAT网关Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|返回白名单列表的详细信息|**Yes**|
|TotalCount|int|白名单资源列表的总的个数|**Yes**|

## GetAvailableResourceForWhiteListDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceId|string|资源类型Id|**Yes**|
|ResourceName|string|资源名称|**Yes**|
|PrivateIP|string|资源的内网Ip|**Yes**|
|ResourceType|string|资源类型|**Yes**|
|VPCId|string|资源所属VPCId|**Yes**|
|SubnetworkId|string|资源所属子网Id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetAvailableResourceForWhiteList
&Region=xxx
&ProjectId=xxx
&NATGWId=CuqLxGDE
```

# Response Example
```
{
    "Action": "GetAvailableResourceForWhiteListResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "ResourceType": "xxxx", 
            "ResourceId": "xxxx", 
            "PrivateIP": "xxxx"
        }
    ]
}
```

