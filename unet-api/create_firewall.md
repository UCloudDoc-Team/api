# 创建防火墙-CreateFirewall

创建防火墙

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写|No|
|Rule.n|string|防火墙规则，例如：TCP\|22\|192.168.1.1/22\|DROP\|LOW\|禁用22端口，第一个参数代表协议：第二个参数代表端口号，第三个参数为ip，第四个参数为ACCEPT（接受）和DROP（拒绝），第五个参数优先级：HIGH（高），MEDIUM（中），LOW（低），第六个参数为该条规则的自定义备注,bj1不支持添加备注|**Yes**|
|Name|string|防火墙名称|**Yes**|
|Tag|string|防火墙业务组，默认为Default|No|
|Remark|string|防火墙描述，默认为空|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|FWId|string|防火墙ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateFirewall
&ProjectId=org-XXXX
&Region=cn-north
&Name=NewFirewall
&Tag=Default
&Rule.0=UDP|53|0.0.0.0/0|ACCEPT|HIGH
&Rule.1=TCP|0-56636|0.0.0.0/0|ACCEPT|HIGH
&Rule.2=TCP|3306|0.0.0.0/0|DROP|HIGH
```

# Response Example
```
{
    "Action": "CreateFirewallResponse", 
    "FWId": "dzPBwJgP", 
    "RetCode": 0
}
```

