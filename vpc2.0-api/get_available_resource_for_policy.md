# 获取NAT网关可配置端口转发规则的资源信息-GetAvailableResourceForPolicy

获取NAT网关可配置端口转发规则的资源信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NATGWId|string|NAT网关Id|**Yes**|
|Limit|int|返回数据长度，默认为10000|No|
|Offset|int|列表起始位置偏移量，默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|支持资源类型的信息|**Yes**|

## GetAvailableResourceForPolicyDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceId|string|资源的Id|**Yes**|
|PrivateIP|string|资源对应的内网Ip|**Yes**|
|ResourceType|string|资源类型。"uhost"：云主机； "upm"，物理云主机； "hadoophost"：hadoop节点； "fortresshost"：堡垒机： "udockhost"，容器|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetAvailableResourceForPolicy
&Region=xxx
&ProjectId=xxx
&NATGWId=CuqLxGDE
&Limit=1000
&Offset=0
```

# Response Example
```
{
    "Action": "GetAvailableResourceForPolicyResponse", 
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

