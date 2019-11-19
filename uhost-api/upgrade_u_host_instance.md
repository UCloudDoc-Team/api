# 热升级UHost实例-UpgradeUHostInstance

在线升级UHost实例的资源配置，目前仅支持CPU核心数，内存容量大小。请注意，由于热升级的实现原因，内存的升级无法跨越过多的内存档位，例如：您只能从1024MB内存升级到2048MB内存。具体限制请查询控制台。

!> 此API仅用于CPU，内存的热升级，无法支持在线更改到更低的配置。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|UHostId|int|UHost实例ID。参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance)|**Yes**|
|CPU|int|目标升级的虚拟CPU核数，单位：个。最小值为1。默认值为当前实例的CPU核数。不同机型支持的CPU范围不同，请参考控制台。|No|
|Memory|int|目标升级的内存大小，单位：MB。默认值为当前实例的内存大小。由于热升级的实现原因，内存的升级无法跨越过多的内存档位，例如：您只能从1024MB内存升级到2048MB内存。具体限制请查询控制台。|No|
|CouponId|string|升级中使用的代金券ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UhostId|string|UHost实例ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=UpgradeUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&UHostId=uhost-xxx
&CPU=4
&Memory=2048
```

# Response Example
```
{
    "Action": "UpgradeUHostInstanceResponse", 
    "RetCode": 0
}
```

