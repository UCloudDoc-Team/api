# 获取云数据库信息-DescribeUDBInstance

获取UDB实例信息，支持两类操作：（1）指定DBId用于获取该db的信息；（2）指定ClassType、Offset、Limit用于列表操作，查询某一个类型db。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区，不填时默认全部可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ClassType|string|DB种类，如果是列表操作，则需要指定,不区分大小写，其取值如下：mysql: SQL；mongo: NOSQL；postgresql: postgresql|No|
|Offset|int|分页显示起始偏移位置，列表操作时必填|No|
|Limit|int|分页显示数量，列表操作时必填|No|
|DBId|string|DB实例id，如果指定则获取单个db实例的描述，否则为列表操作。 指定DBId时无需填写ClassType、Offset、Limit|No|
|IsInUDBC|bool|是否查看专区里面DB|No|
|UDBCId|string|IsInUDBC为True,UDBCId为空，说明查看整个可用区的专区的db，如果UDBId不为空则只查看此专区下面的db|No|
|IncludeSlaves|bool|当只获取这个特定DBId的信息时，如果有该选项，那么把这个DBId实例的所有从库信息一起拉取并返回|No|

?> 指定DBId时无需填写ClassType、Offset、Limit，如不指定DBId时则必须填写

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|DB实例信息列表 UDBInstanceSet|No|
|TotalCount|int|用户db组的数量，对于 mysql: 主从结对数量，没有slave，则只有master mongodb: 副本集数量|No|

## UDBInstanceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|DB实例所在可用区|No|
|CluserRole|string|当DB类型为mongodb时，返回该实例所在集群中的角色，包括：mongos、configsrv_sccc、configsrv_csrs、shardsrv_datanode、shardsrv_arbiter，其中congfigsrv分为sccc和csrs两种模式，shardsrv分为datanode和arbiter两种模式|No|
|DBId|string|DB实例id|No|
|Name|string|实例名称，至少6位|No|
|DBTypeId|string|DB类型id，mysql/mongodb按版本细分各有一个id 目前id的取值范围为[1,7],数值对应的版本如下： 1：mysql-5.5，2：mysql-5.1，3：percona-5.5 4：mongodb-2.4，5：mongodb-2.6，6：mysql-5.6， 7：percona-5.6|No|
|ParamGroupId|int|DB实例使用的配置参数组id|No|
|AdminUser|string|管理员帐户名，默认root|No|
|VirtualIP|string|DB实例虚ip|No|
|VirtualIPMac|string|DB实例虚ip的mac地址|No|
|VPCId|string|VPC的ID|No|
|SubnetId|string|子网ID|No|
|InstanceType|string|UDB数据库机型|No|
|InstanceTypeId|int|UDB数据库机型ID|No|
|Tag|string|获取资源其他信息|No|
|Port|int|端口号，mysql默认3306，mongodb默认27017|No|
|SrcDBId|string|对mysql的slave而言是master的DBId，对master则为空， 对mongodb则是副本集id|No|
|BackupCount|int|备份策略，不可修改，备份文件保留的数量，默认7次|No|
|BackupBeginTime|int|备份策略，不可修改，开始时间，单位小时计，默认3点|No|
|BackupDuration|int|备份策略，一天内备份时间间隔，单位小时，默认24小时|No|
|BackupBlacklist|string|备份策略，备份黑名单，mongodb则不适用|No|
|State|string|DB状态标记 Init：初始化中，Fail：安装失败，Starting：启动中，Running：运行，Shutdown：关闭中，Shutoff：已关闭，Delete：已删除，Upgrading：升级中，Promoting：提升为独库进行中，Recovering：恢复中，Recover fail：恢复失败|No|
|CreateTime|int|DB实例创建时间，采用UTC计时时间戳|No|
|ModifyTime|int|DB实例修改时间，采用UTC计时时间戳|No|
|ExpiredTime|int|DB实例过期时间，采用UTC计时时间戳|No|
|ChargeType|string|Year， Month， Dynamic，Trial，默认: Dynamic|No|
|MemoryLimit|int|内存限制(MB)，默认根据配置机型|No|
|DiskSpace|int|磁盘空间(GB), 默认根据配置机型|No|
|UseSSD|bool|是否使用SSD|No|
|SSDType|string|SSD类型，SATA/PCI-E|No|
|Role|string|DB实例角色，mysql区分master/slave，mongodb多种角色|No|
|DiskUsedSize|float|DB实例磁盘已使用空间，单位GB|No|
|DataFileSize|float|DB实例数据文件大小，单位GB|No|
|SystemFileSize|float|DB实例系统文件大小，单位GB|No|
|LogFileSize|float|DB实例日志文件大小，单位GB|No|
|BackupDate|string|备份日期标记位。共7位,每一位为一周中一天的备份情况 0表示关闭当天备份,1表示打开当天备份。最右边的一位 为星期天的备份开关，其余从右到左依次为星期一到星期 六的备份配置开关，每周必须至少设置两天备份。 例如：1100000 表示打开星期六和星期五的自动备份功能|No|
|InstanceMode|string|UDB实例模式类型, 可选值如下: “Normal”： 普通版UDB实例 “HA”: 高可用版UDB实例|No|
|DataSet|array|如果在需要返回从库的场景下，返回该DB实例的所有从库DB实例信息列表。列表中每一个元素的内容同UDBSlaveInstanceSet 。如果这个DB实例没有从库的情况下，此时返回一个空的列表|No|
|BackupZone|string|跨可用区高可用备库所在可用区|No|

## UDBSlaveInstanceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|可用区|No|
|DBId|string|DB实例id|No|
|Name|string|实例名称，至少6位|No|
|DBTypeId|string|DB类型id，mysql/mongodb按版本细分各有一个id 目前id的取值范围为[1,7],数值对应的版本如下： 1：mysql-5.5，2：mysql-5.1，3：percona-5.5 4：mongodb-2.4，5：mongodb-2.6，6：mysql-5.6， 7：percona-5.6|No|
|ParamGroupId|int|DB实例使用的配置参数组id|No|
|AdminUser|string|管理员帐户名，默认root|No|
|VirtualIP|string|DB实例虚ip|No|
|VirtualIPMac|string|DB实例虚ip的mac地址|No|
|Port|int|端口号，mysql默认3306，mongodb默认27017|No|
|SrcDBId|string|对mysql的slave而言是master的DBId，对master则为空， 对mongodb则是副本集id|No|
|BackupCount|int|备份策略，不可修改，备份文件保留的数量，默认7次|No|
|BackupBeginTime|int|备份策略，不可修改，开始时间，单位小时计，默认3点|No|
|BackupDuration|int|备份策略，一天内备份时间间隔，单位小时，默认24小时|No|
|BackupBlacklist|string|备份策略，备份黑名单，mongodb则不适用|No|
|State|string|DB状态标记 Init：初始化中，Fail：安装失败，Starting：启动中，Running：运行，Shutdown：关闭中，Shutoff：已关闭，Delete：已删除，Upgrading：升级中，Promoting：提升为独库进行中，Recovering：恢复中，Recover fail：恢复失败|No|
|CreateTime|int|DB实例创建时间，采用UTC计时时间戳|No|
|ModifyTime|int|DB实例修改时间，采用UTC计时时间戳|No|
|ExpiredTime|int|DB实例过期时间，采用UTC计时时间戳|No|
|ChargeType|string|Year， Month， Dynamic，Trial，默认: Dynamic|No|
|MemoryLimit|int|内存限制(MB)，默认根据配置机型|No|
|DiskSpace|int|磁盘空间(GB), 默认根据配置机型|No|
|UseSSD|bool|是否使用SSD|No|
|SSDType|string|SSD类型，SATA/PCI-E|No|
|Role|string|DB实例角色，mysql区分master/slave，mongodb多种角色|No|
|DiskUsedSize|float|DB实例磁盘已使用空间，单位GB|No|
|DataFileSize|float|DB实例数据文件大小，单位GB|No|
|SystemFileSize|float|DB实例系统文件大小，单位GB|No|
|LogFileSize|float|DB实例日志文件大小，单位GB|No|
|BackupDate|string|备份日期标记位。共7位,每一位为一周中一天的备份情况 0表示关闭当天备份,1表示打开当天备份。最右边的一位 为星期天的备份开关，其余从右到左依次为星期一到星期 六的备份配置开关，每周必须至少设置两天备份。 例如：1100000 表示打开星期六和星期五的自动备份功能|No|
|InstanceMode|string|UDB实例模式类型, 可选值如下: "Normal": 普通版UDB实例;"HA": 高可用版UDB实例|No|
|ClusterRole|string|当DB类型为mongodb时，返回该实例所在集群中的角色，包括：mongos、configsrv_sccc、configsrv_csrs、shardsrv_datanode、shardsrv_arbiter，其中congfigsrv分为sccc和csrs两种模式，shardsrv分为datanode和arbiter两种模式|No|
|SubnetId|string|子网ID|No|
|VPCId|string|VPC的ID|No|
|InstanceType|string|UDB数据库机型|No|
|InstanceTypeId|int|UDB数据库机型ID|No|
|Tag|string|获取资源其他信息|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ClassType=sql
&Offset=0     
&Limit=3    
```

# Response Example
```
{
    "Action": "DescribeUDBInstanceResponse", 
    "TotalCount": 2, 
    "RetCode": 0, 
    "DataSet": [
        {
            "ParamGroupId": 5829, 
            "SystemFileSize": 0.16965484619140625, 
            "DBTypeId": "mysql-5.6", 
            "DiskSpace": 30, 
            "DBId": "udbha-xxxxx", 
            "DataSet": [
                {
                    "ParamGroupId": 10, 
                    "SystemFileSize": 0.6600914001464844, 
                    "DBTypeId": "mysql-5.6", 
                    "DiskSpace": 30, 
                    "DBId": "udb-xxxxx", 
                    "Port": 3306, 
                    "InstanceMode": "Normal", 
                    "State": "Running", 
                    "ExpiredTime": 1410374400, 
                    "Role": "slave", 
                    "LogFileSize": 0.6138687133789062, 
                    "VirtualIP": "10.10.xxx.xxx", 
                    "CPU": 6, 
                    "VPCId": "uvnet-xxxxx", 
                    "InstanceTypeId": 7, 
                    "AdminUser": "root", 
                    "UseSSD": false, 
                    "SrcDBId": "udbha-xxxxx", 
                    "InstanceType": "Normal", 
                    "BackupBeginTime": 2, 
                    "BackupDate": "0000110", 
                    "SubnetId": "subnet-xxxx", 
                    "SSDType": "", 
                    "BackupCount": 7, 
                    "Name": "slave_01", 
                    "Zone": "cn-bj2-04", 
                    "ModifyTime": 1418107163, 
                    "IsForceDump": 0, 
                    "BackupDuration": 24, 
                    "DiskUsedSize": 3.8427772521972656, 
                    "MemoryLimit": 1500, 
                    "Tag": "Default", 
                    "ChargeType": "Month", 
                    "UDBCId": null, 
                    "DataFileSize": 2.568817138671875, 
                    "VirtualIPMac": "52:54:00:xx:xx:xx", 
                    "CreateTime": 1416970612
                }
            ], 
            "InstanceMode": "HA", 
            "State": "Running", 
            "ExpiredTime": 1410374400, 
            "Role": "master", 
            "EnableRWSplitting": true, 
            "LogFileSize": 0.6411094665527344, 
            "Port": 3306, 
            "CPU": 6, 
            "VPCId": "uvnet-xxxx", 
            "InstanceTypeId": 7, 
            "AdminUser": "root", 
            "UseSSD": true, 
            "SrcDBId": "0eebb346-f2ba-4d05-adc7-xxxxxxxx", 
            "DiskUsedSize": 3.3991432189941406, 
            "BackupBeginTime": 2, 
            "BackupDate": "0000110", 
            "SubnetId": "subnet-xxxxxx", 
            "SSDType": "SATA", 
            "BackupCount": 7, 
            "Name": "james_loaddata", 
            "BackupBlacklist": "", 
            "Zone": "cn-bj2-04", 
            "ModifyTime": 1458107159, 
            "IsForceDump": 0, 
            "InstanceType": "SATA_SSD", 
            "BackupDuration": 24, 
            "VirtualIP": "10.10.xx.xx", 
            "MemoryLimit": 1500, 
            "Tag": "Default", 
            "ChargeType": "Month", 
            "UDBCId": null, 
            "DataFileSize": 2.58837890625, 
            "VirtualIPMac": "52:54:xx:xx:xx:xx", 
            "CreateTime": 1344810776
        }, 
        {
            "ParamGroupId": 10, 
            "SystemFileSize": 0.16956329345703125, 
            "DBTypeId": "mysql-5.6", 
            "DiskSpace": 20, 
            "DBId": "udbha-xxxxxx", 
            "DataSet": [], 
            "InstanceMode": "HA", 
            "State": "Running", 
            "ExpiredTime": 1470374400, 
            "Role": "master", 
            "EnableRWSplitting": false, 
            "LogFileSize": 0.001251220703125, 
            "Port": 3306, 
            "CPU": 6, 
            "VPCId": "uvnet-xxxxx", 
            "InstanceTypeId": 7, 
            "AdminUser": "root", 
            "UseSSD": true, 
            "SrcDBId": "c0de49d4-11ef-442a-b36f-xxxxxxxx", 
            "DiskUsedSize": 1.2706451416015625, 
            "BackupBeginTime": 4, 
            "BackupDate": "1111111", 
            "SubnetId": "subnet-xxxxx", 
            "SSDType": "SATA", 
            "BackupCount": 7, 
            "Name": "test_linshi", 
            "BackupBlacklist": "", 
            "Zone": "cn-bj2-04", 
            "ModifyTime": 1469488504, 
            "IsForceDump": 0, 
            "InstanceType": "SATA_SSD", 
            "BackupDuration": 24, 
            "VirtualIP": "10.17.xx.xx", 
            "MemoryLimit": 1000, 
            "Tag": "Default", 
            "ChargeType": "Month", 
            "UDBCId": null, 
            "DataFileSize": 1.0998306274414062, 
            "VirtualIPMac": "52:54:00:xx:xx:xx", 
            "CreateTime": 1429465675
        }
    ]
}
```

