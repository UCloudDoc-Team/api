# 获取防火墙信息-DescribeFirewall

获取防火墙组信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写|No|
|FWId|string|防火墙ID，默认为返回所有防火墙|No|
|ResourceType|string|绑定防火墙组的资源类型，默认为全部资源类型。枚举值为："unatgw"，NAT网关； "uhost"，云主机； "upm"，物理云主机； "hadoophost"，hadoop节点； "fortresshost"，堡垒机； "udhost"，私有专区主机；"udockhost"，容器；"dbaudit"，数据库审计.|No|
|ResourceId|string|绑定防火墙组的资源ID|No|
|Limit|string|返回数据长度，默认为20，最大10000000|No|
|Offset|string|列表起始位置偏移量，默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|获取的防火墙组详细信息 参见 FirewallDataSet|No|

## FirewallDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|FWId|string|防火墙ID|**Yes**|
|GroupId|int|安全组ID（即将废弃）|**Yes**|
|Name|string|防火墙名称|No|
|Tag|string|防火墙业务组|No|
|Remark|string|防火墙备注|No|
|ResourceCount|int|防火墙绑定资源数量|No|
|CreateTime|int|防火墙组创建时间，格式为Unix Timestamp|No|
|Type|string|防火墙组类型，枚举值为： "user defined", 用户自定义防火墙； "recommend web", 默认Web防火墙； "recommend non web", 默认非Web防火墙|No|
|Rule|array|防火墙组中的规则列表，参见 FirewallRuleSet|No|

## FirewallRuleSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SrcIP|string|源地址|No|
|Priority|string|优先级|No|
|ProtocolType|string|协议类型|No|
|DstPort|string|目标端口|No|
|RuleAction|string|防火墙动作|No|
|Remark|string|防火墙规则备注|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeFirewall
&Region=cn-xxx
```

# Response Example
```
{
    "Action": "DescribeFirewallResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "Remark": "\u5f00\u653e22\uff0c3389\u7aef\u53e3\u548cICMP", 
            "ResourceCount": 0, 
            "Name": "\u975eWeb\u670d\u52a1\u5668\u63a8\u8350(22\uff0c3389)", 
            "Rule": [
                {
                    "Priority": "HIGH", 
                    "ProtocolType": "TCP", 
                    "DstPort": "22", 
                    "RuleAction": "ACCEPT", 
                    "SrcIP": "0.0.0.0/0"
                }, 
                {
                    "Priority": "HIGH", 
                    "ProtocolType": "TCP", 
                    "DstPort": "3389", 
                    "RuleAction": "ACCEPT", 
                    "SrcIP": "0.0.0.0/0"
                }, 
                {
                    "Priority": "HIGH", 
                    "ProtocolType": "ICMP", 
                    "DstPort": "", 
                    "RuleAction": "ACCEPT", 
                    "SrcIP": "0.0.0.0/0"
                }
            ], 
            "GroupId": "25575", 
            "FWId": "firewall-XXXX", 
            "Tag": "Default", 
            "Type": "recommend non web", 
            "CreateTime": 1508472648
        }
    ]
}
```

