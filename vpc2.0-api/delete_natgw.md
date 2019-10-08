# 删除NAT网关-DeleteNATGW

删除NAT网关

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|NATGWId|string|NAT网关Id|**Yes**|
|ReleaseEip|bool|是否释放绑定的EIP。true：解绑并释放；false：只解绑不释放。默认为false|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteNATGW
&Region=xxx
&ProjectId=xxx
&NATGWId=pASxpEhH
&ReleaseEip=true
```

# Response Example
```
{
    "Action": "DeleteNATGWResponse", 
    "RetCode": 0
}
```

