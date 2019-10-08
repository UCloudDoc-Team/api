# 展示NAT网关端口转发规则-DescribeNATGWPolicy

展示NAT网关端口转发规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|NATGWId|string|NAT网关Id|**Yes**|
|Limit|int|返回数据长度，默认为10000|No|
|Offset|int|列表起始位置偏移量，默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的转发策略总数|**Yes**|
|DataSet|array|查到的NATGW 转发策略的详细信息|No|

## NATGWPolicyDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|NATGWId|string|NAT网关Id|**Yes**|
|PolicyId|string|转发策略Id|**Yes**|
|Protocol|string|协议类型|**Yes**|
|SrcEIP|string|端口转发前端EIP|**Yes**|
|SrcEIPId|string|端口转发前端EIP Id|**Yes**|
|SrcPort|string|源端口|**Yes**|
|DstIP|string|目的地址|**Yes**|
|DstPort|string|目的端口|**Yes**|
|PolicyName|string|转发策略名称|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeNATGWPolicy
&Region=xxx
&ProjectId=xxx
&NATGWId=NdvawRZz
&Limit=1000
&Offset=0
```

# Response Example
```
{
    "Action": "DescribeNATGWPolicyResponse", 
    "TotalCount": 2, 
    "RetCode": 0, 
    "DataSet": [
        {
            "PolicyName": "port_80", 
            "DstIP": "10.0.0.190", 
            "Protocol": "TCP", 
            "SrcEIPId": "eip-aeeiew", 
            "SrcPort": "80", 
            "PolicyId": "policy-sh2Qhg", 
            "SrcEIP": "106.75.101.196", 
            "DstPort": "80", 
            "NATGWId": "natgw-anbgfu"
        }, 
        {
            "PolicyName": "port_81", 
            "DstIP": "10.0.2.71", 
            "Protocol": "TCP", 
            "SrcEIPId": "eip-aeeiew", 
            "SrcPort": "22", 
            "PolicyId": "policy-vQyaKW", 
            "SrcEIP": "106.75.101.196", 
            "DstPort": "0", 
            "NATGWId": "natgw-anbgfu"
        }
    ]
}
```

