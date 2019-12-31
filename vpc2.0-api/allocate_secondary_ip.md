# 分配ip-AllocateSecondaryIp

分配ip（用于uk8s使用）

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|Mac|string|节点mac|**Yes**|
|ObjectId|string|资源Id|**Yes**|
|SubnetId|string|子网Id（若未指定，则根据zone获取默认子网进行创建）|No|
|VPCId|string|vpcId|No|
|Ip|string|指定Ip分配|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|IpInfo|object||**Yes**|

## IpInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Ip|string||No|
|Mask|string||No|
|Gateway|string||No|
|Mac|string||No|
|SubnetId|string||No|
|VPCId|string||No|

# Request Example
```
https://api.ucloud.cn/?Action=AllocateSecondaryIp
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=rvlPceNj
&ObjectId=ttFJuSUK
&Mac=hYZEoFAm
&SubnetId=ZFUgcsnL
```

# Response Example
```
{
    "Action": "AllocateSecondaryIpResponse", 
    "IpInfo": {
        "VPCId": "uvnet-XXXX", 
        "IpType": 0, 
        "AzId": 0, 
        "OtherIpMask": "", 
        "Ip": "XX.XX.XX.XXX", 
        "Mask": "255.255.XXX.X", 
        "VIP": null, 
        "ZoneId": 0, 
        "Mac": "XX:XX:XX:XX:XX:XX", 
        "SubnetworkId": "subnet-XXXX", 
        "SubnetworkType": 0, 
        "PipId": "", 
        "AccountId": 0, 
        "ObjectId": "", 
        "Gateway": "XXX.XXX.XX.X", 
        "OtherIp": "", 
        "OperatorId": 0
    }, 
    "RetCode": 0
}
```

