# 获取防火墙信息-DescribeUEdnFirewall

获取防火墙信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FirewallId|string|防火墙ID，默认为返回所有防火墙|No|
|ResourceId|string|绑定防火墙组的资源ID|No|
|Limit|int|返回数据长度，默认为20|No|
|Offset|int|列表起始位置偏移量，默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|FirewallSet|array|防火墙组详细信息，参见 FirewallInfo|No|
|TotalCount|int|满足条件的节点总数|No|

## FirewallInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|FirewallId|string|防火墙Id|**Yes**|
|Name|string|防火墙名称|**Yes**|
|CreateTime|int|创建时间|**Yes**|
|Rule|array|防火墙规则组，详情参见RuleInfo|**Yes**|
|ResourceCount|int|防火墙绑定资源数量|**Yes**|
|Type|string|防火墙组类型，枚举值为： "user defined", 用户自定义防火墙； "recommend web", 默认Web防火墙； "recommend non web", 默认非Web防火墙|**Yes**|
|Remark|string|描述|No|

## RuleInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProtocolType|string|协议，可选值：TCP，UDP，ICMP|**Yes**|
|Port|string|端口，范围用"-"符号分隔，如：1-65535|**Yes**|
|SrcIp|string|源ip|**Yes**|
|Action|string|ACCEPT（接受）和DROP（拒绝）|**Yes**|
|Priority|string|优先级：HIGH（高），MEDIUM（中），LOW（低）|**Yes**|
|Remark|string|备注|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUEdnFirewall
&ProjectId=xPoFIUJB
&FirewallId=YWZRSPzx
&ResourceId=EcnAstrT
&Limit=5
&Offset=9
```

# Response Example
```
{
    "Action": "DescribeUEdnFirewallResponse", 
    "TotalCount": 2, 
    "FirewallSet": [
        {
            "Remark": "JKgzKkvn", 
            "CreateTime": 5, 
            "FirewallId": "UFxqtfzc", 
            "Rule": [
                {
                    "Remark": "OcsXPSxb", 
                    "ProtocolType": "nudQEVPV", 
                    "Priority": "fKJPcYPI", 
                    "Action": "RsYGyPJm", 
                    "SrcIp": "YTGptNVo", 
                    "Port": "vairJAge"
                }
            ], 
            "Name": "JGzGQQag"
        }
    ], 
    "RetCode": 0
}
```

