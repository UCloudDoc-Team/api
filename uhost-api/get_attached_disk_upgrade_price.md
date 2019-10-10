# 获取挂载磁盘的升级价格-GetAttachedDiskUpgradePrice

获取挂载磁盘的升级价格

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DiskSpace|int|磁盘大小，单位GB，步长为10。取值范围需大于当前磁盘大小，最大值请参考[磁盘类型](api/uhost-api/disk_type)。|**Yes**|
|DiskId|string|磁盘ID。参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance)返回值中的DiskSet。|**Yes**|
|UHostId|string|UHost实例ID。 参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance)。|**Yes**|
|BackupMode|string|磁盘备份方案。枚举值：<br> > NONE，无备份 <br> > DATAARK，数据方舟 <br> 当前磁盘支持的备份模式参考 [磁盘类型](api/uhost-api/disk_type)。默认值为当前的备份模式。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Price|float|升级差价。精度为小数点后2位。|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetAttachedDiskUpgradePrice
&Region=mxTjdPUG
&Zone=GxCoXGWk
&ProjectId=abcdNzFG
&DiskSpace=8
&DiskId=zPpZIRGk
&UHostId=wRVYAONq
&BackupMode=NONE
```

# Response Example
```
{
    "Action": "GetAttachedDiskUpgradePriceResponse", 
    "Price": 3.26, 
    "RetCode": 0
}
```

