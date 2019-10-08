# UDB高可用实例升级为Sentinel版本（不带HAProxy）-SwitchUDBHAToSentinel

UDB高可用实例从HAProxy版本升级为Sentinel版本（不带HAProxy）

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|UDB的实例ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=SwitchUDBHAToSentinel
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=gmHxIXWq
&DBId=gDTVtKmV
```

# Response Example
```
{
    "Action": "SwitchUDBHAToSentinelResponse", 
    "RetCode": 0
}
```

