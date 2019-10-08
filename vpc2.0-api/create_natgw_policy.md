# 添加NAT网关端口转发规则-CreateNATGWPolicy

添加NAT网关端口转发规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|NATGWId|string|NAT网关Id|**Yes**|
|Protocol|string|协议类型。枚举值为：TCP、UDP|**Yes**|
|SrcEIPId|string|源IP。填写对应的EIP Id|**Yes**|
|SrcPort|string|源端口。可填写固定端口，也可填写端口范围。支持的端口范围为1-65535|**Yes**|
|DstIP|string|目标IP。填写对饮的目标IP地址|**Yes**|
|DstPort|string|目标端口。可填写固定端口，也可填写端口范围。支持的端口范围为1-65535|**Yes**|
|PolicyName|string|转发策略名称。默认为空|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PolicyId|string|创建时分配的策略Id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateNATGWPolicy
&Region=xxx
&ProjectId=xxx
&NATGWId=voSmtyDG
&Protocol=TCP
&SrcEIPId=MXCFGaVb
&SrcPort=NIQlfARc
&DstIp=WPpinHDz
&DstPort=NjuwdUIK
&PolicyName=MGnDgSGN
```

# Response Example
```
{
    "Action": "CreateNATGWPolicyResponse", 
    "PolicyId": "FXizRyCb", 
    "RetCode": 0
}
```

