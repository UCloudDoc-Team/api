# 获取弹性IP计费方式-GetEIPPayMode

获取弹性IP计费模式

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|EIPId.n|string|弹性IP的资源Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|EIPPayMode|array|EIP的计费模式, 参见 EIPPayModeSet|No|

## EIPPayModeSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|EIPId|string|EIP的资源ID|No|
|EIPPayMode|string|EIP的计费模式. 枚举值为：Bandwidth, 带宽计费;Traffic, 流量计费; "ShareBandwidth",共享带宽模式|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetEIPPayMode
&Region=cn-bj2
&EIPId=eip-eij2r4
```

# Response Example
```
{
    "Action": "GetEIPPayModeResponse", 
    "EIPPayMode": [
        {
            "EIPPayMode": "Traffic", 
            "EIPId": "eip-eij2r4"
        }
    ], 
    "RetCode": 0
}
```

