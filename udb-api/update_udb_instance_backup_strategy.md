# 修改UDB自动备份策略-UpdateUDBInstanceBackupStrategy

修改UDB自动备份策略

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|主节点的Id|**Yes**|
|BackupTime|int|备份的整点时间，范围[0,23]|No|
|BackupDate|string|备份时期标记位。共7位，每一位为一周中一天的备份情况，0表示关闭当天备份，1表示打开当天备份。最右边的一位为星期天的备份开关，其余从右到左依次为星期一到星期六的备份配置开关，每周必须至少设置两天备份。例如：1100000表示打开星期六和星期五的备份功能|No|
|ForceDump|bool|当导出某些数据遇到问题后，是否强制导出其他剩余数据默认是false需要同时设置BackupDate字段|No|
|BackupMethod|string|选择默认的备份方式，可选 snapshot 表示使用快照/物理备份，不填或者其它任何值为默认的逻辑备份。需要同时设置BackupDate字段。（注意现在只有SSD 版本的 MySQL实例支持物理备份）|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.spark.ucloud.cn/?Action=UpdateUDBInstanceBackupStrategy  
&Region=cn-bj2
&ProjectId=7                          
&DBId=udb-xxx
&BackupTime=5
&BackupDate=0011111
&BackupMethod=rjlwkIlW
```

# Response Example
```
{
    "Action": "UpdateUDBInstanceBackupStrategyResponse", 
    "RetCode": 0
}
```

