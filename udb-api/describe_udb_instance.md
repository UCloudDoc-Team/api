# 获取云数据库信息 - DescribeUDBInstance

## 简介

获取UDB实例信息，支持两类操作：（1）指定DBId用于获取该db的信息；（2）指定ClassType、Offset、Limit用于列表操作，查询某一个类型db。

?> 指定DBId时无需填写ClassType、Offset、Limit，如不指定DBId时则必须填写




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区，不填时默认全部可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClassType** | string | DB种类，如果是列表操作，则需要指定,不区分大小写，其取值如下：mysql: SQL；mongo: NOSQL；postgresql: postgresql |No|
| **Offset** | int | 分页显示起始偏移位置，列表操作时必填 |No|
| **Limit** | int | 分页显示数量，列表操作时必填 |No|
| **DBId** | string | DB实例id，如果指定则获取单个db实例的描述，否则为列表操作。 指定DBId时无需填写ClassType、Offset、Limit |No|
| **IsInUDBC** | boolean | 是否查看专区里面DB |No|
| **UDBCId** | string | IsInUDBC为True,UDBCId为空，说明查看整个可用区的专区的db，如果UDBId不为空则只查看此专区下面的db |No|
| **IncludeSlaves** | boolean | 当只获取这个特定DBId的信息时，如果有该选项，那么把这个DBId实例的所有从库信息一起拉取并返回 |No|
| **VPCId** | string | 根据VPCId筛选DB |No|
| **Tag** | string | 根据 业务组 筛选DB |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UDBInstanceSet*](#UDBInstanceSet)] | DB实例信息列表 UDBInstanceSet |No|
| **TotalCount** | int | 用户db组的数量，对于 mysql: 主从结对数量，没有slave，则只有master mongodb: 副本集数量 |No|

#### 数据模型


#### UDBInstanceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | DB实例所在可用区 |No|
| **CaseSensitivityParam** | int | 0区分大小写, 1不分区 |No|
| **ClusterRole** | string | 当DB类型为mongodb时，返回该实例所在集群中的角色，包括：mongos、configsrv_sccc、configsrv_csrs、shardsrv_datanode、shardsrv_arbiter，其中congfigsrv分为sccc和csrs两种模式，shardsrv分为datanode和arbiter两种模式 |No|
| **DBId** | string | DB实例id |No|
| **Name** | string | 实例名称，至少6位 |No|
| **DBTypeId** | string | DB类型id，mysql/mongodb按版本细分各有一个id 目前id的取值范围为[1,7],数值对应的版本如下： 1：mysql-5.5，2：mysql-5.1，3：percona-5.5 4：mongodb-2.4，5：mongodb-2.6，6：mysql-5.6， 7：percona-5.6 |No|
| **ParamGroupId** | int | DB实例使用的配置参数组id |No|
| **AdminUser** | string | 管理员帐户名，默认root |No|
| **VirtualIP** | string | DB实例虚ip |No|
| **VirtualIPMac** | string | DB实例虚ip的mac地址 |No|
| **VPCId** | string | VPC的ID |No|
| **SubnetId** | string | 子网ID |No|
| **InstanceType** | string | UDB数据库机型 |No|
| **InstanceTypeId** | int | UDB数据库机型ID (已弃用) |No|
| **Tag** | string | 获取资源其他信息 |No|
| **Port** | int | 端口号，mysql默认3306，mongodb默认27017 |No|
| **SrcDBId** | string | 对mysql的slave而言是master的DBId，对master则为空， 对mongodb则是副本集id |No|
| **BackupCount** | int | 备份策略，不可修改，备份文件保留的数量，默认7次 |No|
| **BackupBeginTime** | int | 备份策略，不可修改，开始时间，单位小时计，默认3点 |No|
| **BackupDuration** | int | 备份策略，一天内备份时间间隔，单位小时，默认24小时 |No|
| **BackupBlacklist** | string | 备份策略，备份黑名单，mongodb则不适用 |No|
| **State** | string | DB状态标记 Init：初始化中，Fail：安装失败，Starting：启动中，Running：运行，Shutdown：关闭中，Shutoff：已关闭，Delete：已删除，Upgrading：升级中，Promoting：提升为独库进行中，Recovering：恢复中，Recover fail：恢复失败, Remakeing:重做中,RemakeFail:重做失败，VersionUpgrading:小版本升级中，VersionUpgradeWaitForSwitch:高可用等待切换，VersionUpgradeFail：小版本升级失败，UpdatingSSL：修改SSL中，UpdateSSLFail：修改SSL失败,MajorVersionUpgrading:小版本升级中，MajorVersionUpgradeWaitForSwitch:高可用等待切换，MajorVersionUpgradeFail |No|
| **CreateTime** | int | DB实例创建时间，采用UTC计时时间戳 |No|
| **ModifyTime** | int | DB实例修改时间，采用UTC计时时间戳 |No|
| **ExpiredTime** | int | DB实例过期时间，采用UTC计时时间戳 |No|
| **ChargeType** | string | Year， Month， Dynamic，Trial，默认: Dynamic |No|
| **MemoryLimit** | int | 内存限制(MB)，默认根据配置机型 |No|
| **DiskSpace** | int | 磁盘空间(GB), 默认根据配置机型 |No|
| **UseSSD** | boolean | 是否使用SSD |No|
| **SSDType** | string | SSD类型，SATA/PCI-E/NVMe |No|
| **Role** | string | DB实例角色，mysql区分master/slave，mongodb多种角色 |No|
| **DiskUsedSize** | float | DB实例磁盘已使用空间，单位GB |No|
| **DataFileSize** | float | DB实例数据文件大小，单位GB |No|
| **SystemFileSize** | float | DB实例系统文件大小，单位GB |No|
| **LogFileSize** | float | DB实例日志文件大小，单位GB |No|
| **BackupDate** | string | 备份日期标记位。共7位,每一位为一周中一天的备份情况 0表示关闭当天备份,1表示打开当天备份。最右边的一位 为星期天的备份开关，其余从右到左依次为星期一到星期 六的备份配置开关，每周必须至少设置两天备份。 例如：1100000 表示打开星期六和星期五的自动备份功能 |No|
| **InstanceMode** | string | UDB实例模式类型, 可选值如下: “Normal”： 普通版UDB实例 “HA”: 高可用版UDB实例 |No|
| **DataSet** | array[[*UDBSlaveInstanceSet*](#UDBSlaveInstanceSet)] | 如果在需要返回从库的场景下，返回该DB实例的所有从库DB实例信息列表。列表中每一个元素的内容同UDBSlaveInstanceSet 。如果这个DB实例没有从库的情况下，此时返回一个空的列表 |No|
| **BackupZone** | string | 跨可用区高可用备库所在可用区 |No|
| **IPv6Address** | string | 该实例的ipv6地址 |No|
| **UserUFileData** | [*UFileDataSet*](#UFileDataSet) | 用户转存备份到自己的UFILE配置, 结构参考UFileDataSet |No|
| **DBSubVersion** | string | mysql实例提供具体小版本信息 |No|
| **EnableSSL** | int | mysql是否开启了SSL；1->未开启  2->开启 |No|
| **SSLExpirationTime** | int | SSL到期时间 |No|
| **BackupMethod** | string | 默认的备份方式，nobackup表示不备份， snapshot 表示使用快照备份，logic 表示使用逻辑备份，xtrabackup表示使用物理备份。 |No|
| **MachineType** | string | 数据库机型规格 |No|
| **SpecificationType** | int | 是否使用可选cpu类型规格 |No|
| **CPU** | int | CPU核数 |No|

#### UDBSlaveInstanceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | 可用区 |No|
| **ReplicationDelaySeconds** | int | 延时从库时长 |No|
| **DBId** | string | DB实例id |No|
| **Name** | string | 实例名称，至少6位 |No|
| **DBTypeId** | string | DB类型id，mysql/mongodb按版本细分各有一个id 目前id的取值范围为[1,7],数值对应的版本如下： 1：mysql-5.5，2：mysql-5.1，3：percona-5.5 4：mongodb-2.4，5：mongodb-2.6，6：mysql-5.6， 7：percona-5.6 |No|
| **ParamGroupId** | int | DB实例使用的配置参数组id |No|
| **AdminUser** | string | 管理员帐户名，默认root |No|
| **VirtualIP** | string | DB实例虚ip |No|
| **VirtualIPMac** | string | DB实例虚ip的mac地址 |No|
| **Port** | int | 端口号，mysql默认3306，mongodb默认27017 |No|
| **SrcDBId** | string | 对mysql的slave而言是master的DBId，对master则为空， 对mongodb则是副本集id |No|
| **BackupCount** | int | 备份策略，不可修改，备份文件保留的数量，默认7次 |No|
| **BackupBeginTime** | int | 备份策略，不可修改，开始时间，单位小时计，默认3点 |No|
| **BackupDuration** | int | 备份策略，一天内备份时间间隔，单位小时，默认24小时 |No|
| **BackupBlacklist** | string | 备份策略，备份黑名单，mongodb则不适用 |No|
| **State** | string | DB状态标记 Init：初始化中，Fail：安装失败，Starting：启动中，Running：运行，Shutdown：关闭中，Shutoff：已关闭，Delete：已删除，Upgrading：升级中，Promoting：提升为独库进行中，Recovering：恢复中，Recover fail：恢复失败,Remakeing:重做中,RemakeFail:重做失败, MajorVersionUpgrading:小版本升级中，MajorVersionUpgradeWaitForSwitch:高可用等待切换，MajorVersionUpgradeFail |No|
| **CreateTime** | int | DB实例创建时间，采用UTC计时时间戳 |No|
| **ModifyTime** | int | DB实例修改时间，采用UTC计时时间戳 |No|
| **ExpiredTime** | int | DB实例过期时间，采用UTC计时时间戳 |No|
| **ChargeType** | string | Year， Month， Dynamic，Trial，默认: Dynamic |No|
| **MemoryLimit** | int | 内存限制(MB)，默认根据配置机型 |No|
| **DiskSpace** | int | 磁盘空间(GB), 默认根据配置机型 |No|
| **UseSSD** | boolean | 是否使用SSD |No|
| **SSDType** | string | SSD类型，SATA/PCI-E |No|
| **Role** | string | DB实例角色，mysql区分master/slave，mongodb多种角色 |No|
| **DiskUsedSize** | float | DB实例磁盘已使用空间，单位GB |No|
| **DataFileSize** | float | DB实例数据文件大小，单位GB |No|
| **SystemFileSize** | float | DB实例系统文件大小，单位GB |No|
| **LogFileSize** | float | DB实例日志文件大小，单位GB |No|
| **BackupDate** | string | 备份日期标记位。共7位,每一位为一周中一天的备份情况 0表示关闭当天备份,1表示打开当天备份。最右边的一位 为星期天的备份开关，其余从右到左依次为星期一到星期 六的备份配置开关，每周必须至少设置两天备份。 例如：1100000 表示打开星期六和星期五的自动备份功能 |No|
| **InstanceMode** | string | UDB实例模式类型, 可选值如下: "Normal": 普通版UDB实例;"HA": 高可用版UDB实例 |No|
| **ClusterRole** | string | 当DB类型为mongodb时，返回该实例所在集群中的角色，包括：mongos、configsrv_sccc、configsrv_csrs、shardsrv_datanode、shardsrv_arbiter，其中congfigsrv分为sccc和csrs两种模式，shardsrv分为datanode和arbiter两种模式 |No|
| **SubnetId** | string | 子网ID |No|
| **VPCId** | string | VPC的ID |No|
| **InstanceType** | string | UDB数据库机型 |No|
| **InstanceTypeId** | int | UDB数据库机型ID |No|
| **Tag** | string | 获取资源其他信息 |No|
| **CaseSensitivityParam** | int | 0 区分大小写, 1不区分, 只针对mysql8.0 |No|
| **SpecificationType** | int | 实例计算规格类型，0或不传代表使用内存方式购买，1代表使用内存-cpu可选配比方式购买，需要填写MachineType |No|
| **MachineType** | string | 规格类型ID,当SpecificationType为1时有效 |No|

#### UFileDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TokenID** | string | Ufile的令牌tokenid |No|
| **Bucket** | string | bucket名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ClassType=sql
&Offset=0     
&Limit=3    
&VPCId=HXzwVLcy
&Tag=VEUDumDL
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBInstanceResponse",
  "DataSet": [
    {
      "AdminUser": "root",
      "BackupBeginTime": 2,
      "BackupBlacklist": "",
      "BackupCount": 7,
      "BackupDate": "0000110",
      "BackupDuration": 24,
      "CPU": 6,
      "ChargeType": "Month",
      "CreateTime": 1344810776,
      "DBId": "udbha-xxxxx",
      "DBTypeId": "mysql-5.6",
      "DataFileSize": 2.58837890625,
      "DataSet": [
        {
          "AdminUser": "root",
          "BackupBeginTime": 2,
          "BackupCount": 7,
          "BackupDate": "0000110",
          "BackupDuration": 24,
          "CPU": 6,
          "ChargeType": "Month",
          "CreateTime": 1416970612,
          "DBId": "udb-xxxxx",
          "DBTypeId": "mysql-5.6",
          "DataFileSize": 2.568817138671875,
          "DiskSpace": 30,
          "DiskUsedSize": 3.8427772521972656,
          "ExpiredTime": 1410374400,
          "InstanceMode": "Normal",
          "InstanceType": "Normal",
          "InstanceTypeId": 7,
          "IsForceDump": 0,
          "LogFileSize": 0.6138687133789062,
          "MemoryLimit": 1500,
          "ModifyTime": 1418107163,
          "Name": "slave_01",
          "ParamGroupId": 10,
          "Port": 3306,
          "Role": "slave",
          "SSDType": "",
          "SrcDBId": "udbha-xxxxx",
          "State": "Running",
          "SubnetId": "subnet-xxxx",
          "SystemFileSize": 0.6600914001464844,
          "Tag": "Default",
          "UDBCId": null,
          "UseSSD": false,
          "VPCId": "uvnet-xxxxx",
          "VirtualIP": "10.10.xxx.xxx",
          "VirtualIPMac": "52:54:00:xx:xx:xx",
          "Zone": "cn-bj2-04"
        }
      ],
      "DiskSpace": 30,
      "DiskUsedSize": 3.3991432189941406,
      "EnableRWSplitting": true,
      "ExpiredTime": 1410374400,
      "InstanceMode": "HA",
      "InstanceType": "SATA_SSD",
      "InstanceTypeId": 7,
      "IsForceDump": 0,
      "LogFileSize": 0.6411094665527344,
      "MemoryLimit": 1500,
      "ModifyTime": 1458107159,
      "Name": "james_loaddata",
      "ParamGroupId": 5829,
      "Port": 3306,
      "Role": "master",
      "SSDType": "SATA",
      "SrcDBId": "0eebb346-f2ba-4d05-adc7-xxxxxxxx",
      "State": "Running",
      "SubnetId": "subnet-xxxxxx",
      "SystemFileSize": 0.16965484619140625,
      "Tag": "Default",
      "UDBCId": null,
      "UseSSD": true,
      "VPCId": "uvnet-xxxx",
      "VirtualIP": "10.10.xx.xx",
      "VirtualIPMac": "52:54:xx:xx:xx:xx",
      "Zone": "cn-bj2-04"
    },
    {
      "AdminUser": "root",
      "BackupBeginTime": 4,
      "BackupBlacklist": "",
      "BackupCount": 7,
      "BackupDate": "1111111",
      "BackupDuration": 24,
      "CPU": 6,
      "ChargeType": "Month",
      "CreateTime": 1429465675,
      "DBId": "udbha-xxxxxx",
      "DBTypeId": "mysql-5.6",
      "DataFileSize": 1.0998306274414062,
      "DataSet": [],
      "DiskSpace": 20,
      "DiskUsedSize": 1.2706451416015625,
      "EnableRWSplitting": false,
      "ExpiredTime": 1470374400,
      "InstanceMode": "HA",
      "InstanceType": "SATA_SSD",
      "InstanceTypeId": 7,
      "IsForceDump": 0,
      "LogFileSize": 0.001251220703125,
      "MemoryLimit": 1000,
      "ModifyTime": 1469488504,
      "Name": "test_linshi",
      "ParamGroupId": 10,
      "Port": 3306,
      "Role": "master",
      "SSDType": "SATA",
      "SrcDBId": "c0de49d4-11ef-442a-b36f-xxxxxxxx",
      "State": "Running",
      "SubnetId": "subnet-xxxxx",
      "SystemFileSize": 0.16956329345703125,
      "Tag": "Default",
      "UDBCId": null,
      "UseSSD": true,
      "VPCId": "uvnet-xxxxx",
      "VirtualIP": "10.17.xx.xx",
      "VirtualIPMac": "52:54:00:xx:xx:xx",
      "Zone": "cn-bj2-04"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





