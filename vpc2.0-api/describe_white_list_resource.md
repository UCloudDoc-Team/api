# 展示NAT网关白名单资源列表-DescribeWhiteListResource

展示NAT网关白名单资源列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|NATGWIds.n|string|NAT网关的Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|白名单资源的详细信息，详见DescribeResourceWhiteListDataSet|**Yes**|
|TotalCount|int|白名单资源的总数|**Yes**|

## DescribeWhiteListResourceDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IfOpen|int|0：普通模式，1：白名单模式|**Yes**|
|NATGWId|string|NAT网关Id|**Yes**|
|ObjectIPInfo|array|白名单资源信息|**Yes**|

## DescribeWhiteListResourceObjectIPInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|GwType|string|natgw字符串|**Yes**|
|PrivateIP|string|白名单资源的内网IP|**Yes**|
|ResourceId|string|白名单资源Id信息|**Yes**|
|ResourceName|string|白名单资源名称|**Yes**|
|ResourceType|string|白名单资源类型|**Yes**|
|SubResourceId|string|资源绑定的虚拟网卡的实例ID|**Yes**|
|SubResourceName|string|资源绑定的虚拟网卡的实例名称|**Yes**|
|SubResourceType|string|资源绑定的虚拟网卡的类型|**Yes**|
|VPCId|string|白名单资源所属VPCId|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWhiteListResource
&Region=cn-bj2
&NATGWIds.0=NbbRAeIJ
```

# Response Example
```
{
    "Action": "DescribeWhiteListResourceResponse", 
    "TotalCount": 9, 
    "RetCode": 0, 
    "DataSet": [
        "nSRkanNq", 
        "TkHTtQoc", 
        "ONBPkxrr", 
        "aoGskHfU", 
        "suKalXHG", 
        "UQMozDcj", 
        "JVOeFxGX", 
        "EUbVfeda"
    ]
}
```

