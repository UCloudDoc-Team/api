# 创建从库-CreateUDBSlave

创建UDB实例的slave

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SrcId|string|master实例的DBId,该值可以通过DescribeUDBInstance获取|**Yes**|
|Name|string|实例名称，至少6位|**Yes**|
|Port|int|端口号，mysql默认3306|No|
|UseSSD|bool|是否使用SSD，默认为true|No|
|SSDType|string|SSD类型，可选值为"SATA"、"PCI-E"，如果UseSSD为true ，则必选|No|
|IsLock|bool|是否锁主库，默认为true|No|
|InstanceMode|string|UDB实例部署模式，可选值如下：Normal: 普通单点实例HA: 高可用部署实例|No|
|MemoryLimit|int|内存限制(MB)，目前支持以下几档 1000M/2000M/4000M/ 6000M/8000M/12000M/16000M/ 24000M/32000M/48000M/ 64000M/96000M|No|
|DiskSpace|int|磁盘空间(GB), 暂时支持20G - 3000G（API支持，前端暂时只开放内存定制）|No|
|InstanceType|string|UDB实例类型：Normal和SATA_SSD|No|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DBId|string|创建slave的DBId|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUDBSlave 
&Region=cn-bj2
&SrcId=udb-xxxxx
&Name=udb-xxxxxxx-slave
&Port=3306     
&MemoryLimit=4
&DiskSpace=4
```

# Response Example
```
{
    "Action": "CreateUDBSlaveResponse", 
    "DBId": "udb-xxxxxx", 
    "RetCode": 0
}
```

