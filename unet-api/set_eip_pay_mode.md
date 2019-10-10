# 设置弹性IP计费方式-SetEIPPayMode

设置弹性IP计费模式, 切换时会涉及付费/退费.

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|EIPId|string|弹性IP的资源Id|**Yes**|
|PayMode|string|计费模式. 枚举值："Traffic", 流量计费模式; "Bandwidth", 带宽计费模式|**Yes**|
|Bandwidth|int|调整的目标带宽值, 单位Mbps. 各地域的带宽值范围如下: 流量计费[1-200],其余情况[1-800]|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=SetEIPPayMode
&PayMode=Traffic
&Bandwidth=2
&Region=cn-bj2
&EIPId=eip-XXXXXXX
```

# Response Example
```
{
    "Action": "SetEIPPayModeResponse", 
    "Request_uuid": "903fd858-ef55-416d-9abc-XXXXXX", 
    "RetCode": 0
}
```

