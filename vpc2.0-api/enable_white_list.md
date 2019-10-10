# 修改NAT网关白名单开关-EnableWhiteList

修改NAT网关白名单开关

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NATGWId|string|NAT网关Id|**Yes**|
|IfOpen|int|白名单开关标记。0：关闭；1：开启。默认为0|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=EnableWhiteList
&Region=cn-bj222
&ProjectId=xxxx
&NATGWId=LtarYISU
&IfOpen=0
```

# Response Example
```
{
    "Action": "EnableWhiteListResponse", 
    "RetCode": 0
}
```

