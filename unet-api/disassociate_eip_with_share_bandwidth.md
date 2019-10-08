# 将EIP移出共享带宽-DisassociateEIPWithShareBandwidth

将EIP移出共享带宽

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ShareBandwidthId|string|共享带宽ID|**Yes**|
|Bandwidth|int|移出共享带宽后，EIP的外网带宽, 单位为Mbps. 各地域带宽范围如下：  流量计费[1-200],带宽计费[1-800]|**Yes**|
|EIPIds.n|string|EIP的资源Id；默认移出该共享带宽下所有的EIP|No|
|PayMode|string|移出共享带宽后，EIP的计费模式. 枚举值: "Traffic", 流量计费; "Bandwidth", 带宽计费;  默认为 "Bandwidth".|No|
|IPVersion|string|共享带宽类型，IPv4或者IPv6，不传默认IPv4|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DisassociateEIPWithShareBandwidth
&Region=cn-bj2
&EIPIds.0=eip-XXXXX
&ShareBandwidthId=bwshare-XXXX
&Bandwidth=2
&IPVersion=nHjcpyjh
```

# Response Example
```
{
    "Action": "DisassociateEIPWithShareBandwidthResponse", 
    "Request_uuid": "f46ae8ae-84a3-4736-b49b-XXXXX", 
    "RetCode": 0
}
```

