# 更新防火墙属性-UpdateUEdnFirewallAttribute

更新防火墙名称及描述

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FirewallId|string|防火墙Id|**Yes**|
|Name|string|防火墙名称|No|
|Remark|string|描述|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateUEdnFirewallAttribute
&ProjectId=tdlGxpVZ
&FirewallId=AiKtEMHQ
&Name=VjxHuIJL
&Remark=tzLQetFz
```

# Response Example
```
{
    "Action": "UpdateUEdnFirewallAttributeResponse", 
    "RetCode": 0
}
```

