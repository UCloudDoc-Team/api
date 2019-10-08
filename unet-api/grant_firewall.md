# 应用防火墙-GrantFirewall

将防火墙应用到资源上

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|FWId|string|防火墙资源ID|**Yes**|
|ResourceType|string|绑定防火墙组的资源类型，默认为全部资源类型。枚举值为："unatgw"，NAT网关； "uhost"，云主机； "upm"，物理云主机； "hadoophost"，hadoop节点； "fortresshost"，堡垒机； "udhost"，私有专区主机；"udockhost"，容器；"dbaudit"，数据库审计.|**Yes**|
|ResourceId|string|所应用资源ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GrantFirewall
&ProjectId=org-xxx
&Region=xxxx
&FWId=fw-xxx
&ResourceType=uhost
&ResourceId=uhost-xxx
```

# Response Example
```
{
    "Action": "GrantFirewallResponse", 
    "RetCode": 0
}
```

