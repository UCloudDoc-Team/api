# 删除NAT网关白名单列表-DeleteWhiteListResource

删除NAT网关白名单列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NATGWId|string|NAT网关Id|**Yes**|
|ResourceIds.n|string|删除白名单的资源Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteWhiteListResource
&Region=xxx
&ProjectId=xxx
&NATGWId=hdsKHuCb
&ResourceIds.0=ZPNimgsE
```

# Response Example
```
{
    "Action": "DeleteWhiteListResourceResponse", 
    "RetCode": 0
}
```

