# 创建专区资源池-CreateUDSet

创建专区资源池

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|CPU|string|宿主机CPU核数, 单位:个， 默认值: 32，可取值：32/48|No|
|Memory|string|内存大小, 单位: MB, 范围[65536，163840], 步长: 32768, 默认值: 163840|No|
|DiskSpace|string|数据盘大小, 单位: GB, 范围[4096,6144], 步长: 2048, 默认值: 6144|No|
|Name|string|资源池名称, 默认:ResourceBlock|No|
|Remark|string|资源池备注, 默认:””|No|
|Tag|string|资源池业务组, 默认:Default|No|
|ChargeType|string|Year, Month默认:Year|No|
|Quantity|string|购买时长，默认:1|No|
|Count|string|购买台数，范围[1] 默认:1|No|
|CouponId|string|代金券|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|HostIds|array|资源池的实例短ID|No|

# Request Example
```
https://api.ucloud.cn?Action=CreateUDSetInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&CPU=48
&Memory=163840
&Disk=6144
```

# Response Example
```
{
    "Action": "CreateUDSetResponse", 
    "HostIds": "udset-xxx", 
    "RetCode": 0
}
```

