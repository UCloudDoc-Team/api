# 从数据方舟的备份创建UDisk-CloneUDiskUDataArk

从数据方舟的备份创建UDisk

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|Name|string|实例名称|**Yes**|
|UDiskId|string|需要克隆的源盘id|**Yes**|
|SnapshotTime|int|指定从方舟克隆的备份时间点|**Yes**|
|Comment|string|Disk注释|No|
|ChargeType|string|Year , Month, Dynamic，Postpay 默认: Dynamic|No|
|Quantity|int|购买时长 默认: 1|No|
|UDataArkMode|string|是否开启数据方舟  Yes:开启数据方舟 No:关闭数据方舟 默认:No|No|
|Size|int|购买UDisk大小,单位:GB,范围[1~2000], 权限位控制可达8T,若需要请申请开通相关权限。(UDisk大小设定对本地盘备份有效，对云盘备份无效)|No|
|Tag|string|业务组 默认：Default|No|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UDiskId|array|创建UDisk Id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CloneUDiskUDataArk
&Region=cn-east
&Zone=cn-east-01
&UDiskId=F207B59C-BA54-4455-9CF1-996DB5A7CD22
&Name=xxx
&SnapshotTime=1473646985
&Tag=PgHINlLb
```

# Response Example
```
{
    "Action": "CloneUDiskUDataArkResponse", 
    "RetCode": 0, 
    "UDiskId": "ebi2"
}
```

