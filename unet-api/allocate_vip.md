# 申请内网虚拟IP-AllocateVIP

根据提供信息，申请内网VIP(Virtual IP），多用于高可用程序作为漂移IP。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|VPCId|string|指定vip所属的VPC|**Yes**|
|SubnetId|string|子网id|**Yes**|
|Count|int|申请数量，默认: 1|No|
|Name|string|vip名，默认为VIP|No|
|Tag|string|业务组名称，默认为Default|No|
|Remark|string|备注|No|
|BusinessId|string|业务组|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|VIPSet|array|申请到的VIP资源相关信息|No|
|DataSet|array|申请到的VIP地址|No|

## VIPSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|VIP|string|虚拟ip|No|
|VIPId|string|虚拟ip id|No|
|VPCId|string|VPC id|No|

# Request Example
```
https://api.ucloud.cn/?Action=AllocateVIP
&Region=cn-bj2
&ProjectId=xxxx
&Zone=cn-bj2-04
&VPCId=xxx
&SubnetId=xxx
```

# Response Example
```
{
    "Action": "AllocateVIPResponse", 
    "TotalCount": 1, 
    "DataSet": [
        "10.64.204.72"
    ], 
    "RetCode": 0, 
    "VIPSet": [
        {
            "VIP": "10.64.204.72", 
            "VPCId": "vnet-xxx", 
            "VIPId": "vip-xxx"
        }
    ]
}
```

