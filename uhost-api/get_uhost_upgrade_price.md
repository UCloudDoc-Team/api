# 获取主机规格调整差价-GetUHostUpgradePrice

获取UHost实例升级配置的价格。可选配置范围请参考[云主机机型说明](api/uhost-api/get_uhost_upgrade_price)。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|UHostId|string|UHost实例ID。 参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance)。|**Yes**|
|CPU|int|虚拟CPU核数。可选参数：1-64（可选范围参考控制台）。默认值为当前实例的CPU核数。|No|
|Memory|int|内存大小。单位：MB。范围 ：[1024, 262144]，取值为1024的倍数（可选范围参考控制台）。默认值为当前实例的内存大小。|No|
|NetCapValue|int|网卡升降级（1，表示升级，2表示降级，0表示不变）|No|

?> 若需查询调整磁盘大小的价格，请调用ResizeAttachedDisk。

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|float|规格调整差价。精确到小数点后2位。|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUHostUpgradePrice
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&UHostId=uhost-xxx
&CPU=4

```

# Response Example
```
{
    "Action": "GetUHostUpgradePriceResponse", 
    "Price": 19.96, 
    "RetCode": 0
}
```

