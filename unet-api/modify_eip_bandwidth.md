# 调整弹性IP带宽-ModifyEIPBandwidth

调整弹性IP的外网带宽

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|EIPId|string|弹性IP的资源ID|**Yes**|
|Bandwidth|int|弹性IP的外网带宽, 单位为Mbps. 各地域的带宽值范围如下：流量计费[1-200],带宽计费[1-800]|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyEIPBandwidth
&Region=cn-bj2
&EIPId=eip-XXXX
&Bandwidth=4
```

# Response Example
```
{
    "Action": "ModifyEIPBandwidthResponse", 
    "Request_uuid": "4a6cb657-8b2a-4228-9678-XXXXXX", 
    "RetCode": 0
}
```

