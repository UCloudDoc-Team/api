# 修改UDB实例的配置-ResizeUDBInstance

修改（升级和降级）UDB实例的配置，包括内存和磁盘的配置，对于内存升级无需关闭实例，其他场景需要事先关闭实例。两套参数可以配置升降机：1.配置UseSSD和SSDType  2.配置InstanceType，不需要配置InstanceMode。这两套第二套参数的优先级更高

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DBId|string|实例的Id|**Yes**|
|MemoryLimit|int|内存限制(MB)，目前支持以下几档 1000M/2000M/4000M/ 6000M/8000M/ 12000M/16000M/ 24000M/32000M/ 48000M/64000M/96000M。|**Yes**|
|DiskSpace|int|磁盘空间(GB), 暂时支持20G-3000G|**Yes**|
|UseSSD|bool|是否使用SSD，默认为true|No|
|SSDType|string|SSD类型，可选值为"SATA"、"PCI-E"，如果UseSSD为true ，则必选|No|
|UDBCId|string|专区的ID，如果有值表示专区中的DB配置升降级|No|
|InstanceType|string|UDB数据库机型: "Normal": "标准机型" ,  "SATA_SSD": "SSD机型" , "PCIE_SSD": "SSD高性能机型" ,  "Normal_Volume": "标准大容量机型",  "SATA_SSD_Volume": "SSD大容量机型" ,  "PCIE_SSD_Volume": "SSD高性能大容量机型" |No|
|InstanceMode|string|UDB实例模式类型, 可选值如下: "Normal": 普通版UDB实例 "HA": 高可用版UDB实例 默认是"Normal"|No|
|StartAfterUpgrade|bool|DB关闭状态下升降级，升降级后是否启动DB，默认为false|No|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ResizeUDBInstance
&Region=cn-bj2
&DBId=udb-xxx
&MemoryLimit=15000
&DiskSpace=500
```

# Response Example
```
{
    "Action": "ResizeUDBInstanceResponse", 
    "RetCode": 0
}
```

