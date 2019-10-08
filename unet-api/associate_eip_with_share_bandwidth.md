# 将EIP加入共享带宽-AssociateEIPWithShareBandwidth

将EIP加入共享带宽

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。|No|
|EIPIds.n|string|要加入共享带宽的EIP的资源Id|**Yes**|
|ShareBandwidthId|string|共享带宽ID|**Yes**|
|IPVersion|string|共享带宽类型，IPv4或者IPv6，不传默认IPv4|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=AssociateEIPWithShareBandwidth
&Region=cn-bj2
&EIPIds.0=eip-XXXXX
&ShareBandwidthId=bwshare-XXXXX
&BwType=tcsRSDBP
&IPVersion=iUnPUHzo
```

# Response Example
```
{
    "Action": "AssociateEIPWithShareBandwidthResponse", 
    "Request_uuid": "d4dde503-0b50-451d-943b-XXXXXXXXX", 
    "RetCode": 0
}
```

