# 描述 UDPN-DescribeUDPN

描述 UDPN

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|UDPNId|string|申请到的 UDPN 资源 ID。若为空，则查询该用户在机房所有的专线信息。非默认项目资源，需填写ProjectId|No|
|Offset|int|列表起始位置偏移量，默认为 0|No|
|Limit|int|返回数据长度，默认为 20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|查询到的总数量|**Yes**|
|DataSet|array|UDPN详情|No|

## UDPNData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UDPNId|string|UDPN 资源短 ID|**Yes**|
|Peer1|string|可用区域 1|**Yes**|
|Peer2|string|可用区域 2|**Yes**|
|ChargeType|string|计费类型|**Yes**|
|Bandwidth|int|带宽|**Yes**|
|CreateTime|int|unix 时间戳 创建时间|**Yes**|
|ExpireTime|int|unix 时间戳 到期时间|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDPN
&UDPNId=udpn-uy3qvu
&ProjectId＝test
```

# Response Example
```
{
    "Action": "DescribeUDPNResponse", 
    "TotalCount": 5, 
    "RetCode": 0, 
    "DataSet": [
        {
            "Peer1": "cn-bj2", 
            "Peer2": "cn-gd", 
            "UDPNId": "udpn-uy3qvu", 
            "ExpireTime": 1509465600, 
            "Bandwidth": 2, 
            "ChargeType": "Month", 
            "CreateTime": 1508413095
        }
    ]
}
```

