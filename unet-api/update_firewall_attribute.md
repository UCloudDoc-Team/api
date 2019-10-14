# 更新防火墙属性-UpdateFirewallAttribute

更新防火墙规则

!> note在更新防火墙属性时，新的属性会覆盖掉原有属性。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FWId|string|防火墙资源ID|**Yes**|
|Name|string|防火墙名称，默认为空，为空则不做修改。Name,Tag,Remark必须填写1个及以上|No|
|Tag|string|防火墙业务组，默认为空，为空则不做修改。Name,Tag,Remark必须填写1个及以上|No|
|Remark|string|防火墙备注，默认为空，为空则不做修改。Name,Tag,Remark必须填写1个及以上|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateFirewallAttribute
&ProjectId=org-ji3f1h
&Region=cn-north-01
&FWId=fw-4qgufv
&Remark=Testapi
```

# Response Example
```
{
    "Action": "UpdateFirewallAttributeResponse", 
    "RetCode": 0
}
```

