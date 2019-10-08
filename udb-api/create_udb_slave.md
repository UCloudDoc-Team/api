# 创建从库-CreateUDBSlave

创建UDB实例的slave

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|SrcId|string|master实例的DBId,该值可以通过DescribeUDBInstance获取|**Yes**|
|Name|string|实例名称，至少6位|**Yes**|
|Port|int|端口号，mysql默认3306|No|
|UseSSD|bool|是否使用SSD，默认为false|No|
|SSDType|string|SSD类型，可选值为"SATA"、"PCI-E"，如果UseSSD为true ，则必选|No|
|IsLock|bool|是否锁主库，默认为true|No|
|InstanceMode|string|UDB实例部署模式，可选值如下：Normal: 普通单点实例HA: 高可用部署实例|No|
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
&SrcId=00f9868c-c7f5-4852-9eac-d200b678f0e1
&Name=udb-xxxxxxx-slave
&Port=3306     
```

# Response Example
```
{
    "Action": "CreateUDBSlaveResponse", 
    "DBId": "717b2716-8070-445b-b9e4-55466831bff1", 
    "RetCode": 0
}
```

