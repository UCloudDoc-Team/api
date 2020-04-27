# 绑定防火墙-BindUEdnFirewall

绑定防火墙，应用防火墙规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FirewallId|string|防火墙Id|**Yes**|
|ResourceId|string|节点资源Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=BindUEdnFirewall
&ProjectId=MetSwsUr
&FirewallId=boKrAqio
&ResourceId=lfwMYOuU
```

# Response Example
```
{
    "Action": "BindUEdnFirewallResponse", 
    "RetCode": 0
}
```

