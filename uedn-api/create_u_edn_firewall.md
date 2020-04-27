# 创建外网防火墙-CreateUEdnFirewall

创建外网防火墙

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Name|string|防火墙名称|**Yes**|
|Rule.n.ProtocolType|string|协议，可选值：TCP，UDP，ICMP|**Yes**|
|Rule.n.Port|string|端口，范围用"-"符号分隔，如：1-65535|**Yes**|
|Rule.n.SrcIp|string|源ip|**Yes**|
|Rule.n.Action|string|ACCEPT（接受）和DROP（拒绝）|**Yes**|
|Rule.n.Priority|string|优先级：HIGH（高），MEDIUM（中），LOW（低）|**Yes**|
|Rule.n.Remark|string|备注|No|
|Remark|string|描述|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|FirewallId|string|防火墙Id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUEdnFirewall
&ProjectId=rbDTmgwO
&Name=sXrUJapw
&Rule.n.ProtocolType=CDuDfscH
&Rule.n.Port=xNxveFBb
&Rule.n.SrcIp=eMYhxHAY
&Rule.n.Action=ecYelRsn
&Rule.n.Priority=humEedah
&Rule.n.Remark=moqEoozO
&Remark=nTYQAHpu
```

# Response Example
```
{
    "Action": "CreateUEdnFirewallResponse", 
    "FirewallId": "Xenqfuka", 
    "RetCode": 0
}
```

