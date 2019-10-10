# 更新防火墙规则-UpdateFirewall

更新防火墙规则

```
note
在更新防火墙规则时，新的规则会覆盖掉原有规则。所以若需要更改或加入新的规则，需要将原所有规则与新规则一起提交。
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|FWId|string|防火墙资源ID|**Yes**|
|Rule.n|string|防火墙规则，请见下方说明。|**Yes**|

Rule.n字段说明：防火墙规则，例如：TCP|22|192.168.1.1/22|DROP|LOW|禁用22端口，第一个
参数代表协议：第二个参数代表端口号，第三个参数为ip，第四个参数为ACCEPT（接受）和DRO
P（拒绝），第五个参数优先级：HIGH（高），MEDIUM（中），LOW（低），第六个参数为该
条规则的自定义备注

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|FWId|string|防火墙id|No|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateFirewall
&ProjectId=org-xxx
&Region=xxxx
&FWId=fw-xxxx
&Rule.1=UDP|53|0.0.0.0/0|ACCEPT|50|备注
&Rule.0=TCP|3306|0.0.0.0/0|DROP|50|备注
```

# Response Example
```
{
    "Action": "UpdateFirewallResponse", 
    "FWId": "firewall-xxx", 
    "RetCode": 0
}
```

