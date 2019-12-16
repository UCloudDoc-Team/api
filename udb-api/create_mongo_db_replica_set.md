# 创建DB副本集-CreateMongoDBReplicaSet

一键创建DB副本集

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Name|string|PrimaryDB实例名称，至少6位|**Yes**|
|AdminPassword|string|管理员密码|**Yes**|
|DBTypeId|string|DB类型id对应的字符串形式（例如：mongodb-2.6）注意：当前仅支持mongodb|**Yes**|
|DiskSpace|int|磁盘空间(GB), 暂时支持20G - 3000G|**Yes**|
|ParamGroupId|int|DB实例使用的配置参数组id|**Yes**|
|MemoryLimit|int|内存限制(MB)，目前支持以下几档 1000M/2000M/4000M/ 6000M/8000M/12000M/16000M/ 24000M/32000M/48000M/ 64000M/96000M|**Yes**|
|Port|int|端口号|**Yes**|
|ChargeType|string|Year， Month， Dynamic，Trial，默认: Month|No|
|Quantity|int|购买时长(N个月)，默认值1个月。如果为0，代表购买到月底。|No|
|AdminUser|string|管理员帐户名，默认root|No|
|BackupCount|int|备份策略，每周备份数量，默认7次|No|
|BackupTime|int|备份策略，备份开始时间，单位小时计，默认1点|No|
|BackupDuration|int|备份策略，备份时间间隔，单位小时计，默认24小时|No|
|UseSSD|bool|是否使用SSD，默认为true|No|
|SSDType|string|SSD类型，可选值为"SATA"、"PCI-E"，如果UseSSD为true ，则必选|No|
|CPU|int|cpu核数|No|
|InstanceType|string|UDB数据库机型|No|
|SubnetId|string|子网ID|No|
|VPCId|string|VPC的ID|No|
|ClusterId|string|所属分片集群的ID|No|
|CouponId.n|string|CouponId.0 代表第一个代金券id，对于传入多个代金券id，后面为 CouponId.1, CouponId.2 以此类推|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DBIds|array|返回所有副本集成员的Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateMongoDBReplicaSet
&Region=cosmAFbt
&Zone=xBxVTiMQ
&ProjectId=jrKVXipN
&Name=ydhfcdle
&AdminPassword=IMYNtZID
&DBTypeId=csTyuCveUvRbSNuMEQjiZkVcZdbiJnzuoxyZEfCPaUaMqJkcULmxcWTuGzYIaJdNtyPyfTifdEQIWGFGALkrDbHvVVAiRmdqHvtMBSsnnFRRLSOnMoAKdzSaBPxbEKrwVPZHMtivhOKqIPdMYnnbZklWtPCuHzGdwkfoPQFNAgEzLdxQieISIPOlTBdJYUfLGvCjtzICKdUaSlstsdQMvHluipqJscHJfpzqQBLYJSclSxXLtpxoiDYEjZdGmjeBsVpxcNIKIsRAHLLVLAtzGdsKbmyZphqiTHhjAHvtcmtccHYmqdeYMNLRMingKSPGgEFpqVmkvOrwAngbxiOwCDkgOVstLPwptFuYUfSzopDWOhupQAWKZDVEsADvdcBQTUXzrclMdoQhFusTDPWxmyGfWuwfzlNDgMhGaNWZkNKJQFRiDQgueKwnOvlzKfRuXGserAzG
&DiskSpace=8
&ParamGroupId=8
&MemoryLimit=2
&Quantity=7
&Port=7
&ChargeType=HDrrxEEl
&AdminUser=EbSfMBeG
&BackupCount=3
&BackupTime=2
&BackupDuration=7
&UseSSD=true
&SSDType=TnKaeTIe
&CPU=8
&InstanceType=JSduiQwk
&SubnetId=tjsNjPHZ
&VPCId=mCBucsAy
&ClusterId=LvRXciyw
&CouponId.n=uBpRaUqU
```

# Response Example
```
{
    "Action": "CreateMongoDBReplicaSetResponse", 
    "DBIds": [
        "DUZMytjm"
    ], 
    "RetCode": 0
}
```

