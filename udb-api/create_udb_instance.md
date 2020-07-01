# 创建数据库 - CreateUDBInstance

## 简介

创建UDB实例（包括创建mysql master节点、mongodb primary/configsvr节点和从备份恢复实例）

?> 创建跨可用区的高可用注意项:<br />1. 需要参数 BackupZone：值为高可用容灾的ZoneId<br />2. 参数ParamGroupId: 值为跨可用区的配置文件，可以通过DescribeUDBParamGroup获得




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUDBInstance)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDBInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Name** | string | 实例名称，至少6位 |**Yes**|
| **AdminPassword** | string | 管理员密码 |**Yes**|
| **DBTypeId** | string | DB类型id，mysql/mongodb/postgesql按版本细分 1：mysql-5.1，2：mysql-5.5，3：percona-5.5，4：mysql-5.6，5：percona-5.6，6：mysql-5.7，7：percona-5.7，8：mariadb-10.0，9：mongodb-2.4，10：mongodb-2.6，11：mongodb-3.0，12：mongodb-3.2,13：postgresql-9.4，14：postgresql-9.6，14：postgresql-10.4 |**Yes**|
| **Port** | int | 端口号，mysql默认3306，mongodb默认27017，postgresql默认5432 |**Yes**|
| **DiskSpace** | int | 磁盘空间(GB), 暂时支持20G - 32T |**Yes**|
| **ParamGroupId** | int | DB实例使用的配置参数组id |**Yes**|
| **MemoryLimit** | int | 内存限制(MB)，目前支持以下几档 1000M/2000M/4000M/ 6000M/8000M/12000M/16000M/ 24000M/32000M/48000M/ 64000M/96000M/128000M/192000M/256000M/320000M |**Yes**|
| **ChargeType** | string | Year， Month， Dynamic，Trial，默认: Month |No|
| **Quantity** | int | 购买时长，默认值1 |No|
| **AdminUser** | string | 管理员帐户名，默认root |No|
| **BackupCount** | int | 备份策略，每周备份数量，默认7次 |No|
| **BackupTime** | int | 备份策略，备份开始时间，单位小时计，默认1点 |No|
| **BackupDuration** | int | 备份策略，备份时间间隔，单位小时计，默认24小时 |No|
| **BackupId** | int | 备份id，如果指定，则表明从备份恢复实例 |No|
| **UseSSD** | boolean | 是否使用SSD，默认为true。目前主要可用区、海外机房、新机房只提供SSD资源，非SSD资源不再提供。 |No|
| **SSDType** | string | SSD类型，可选值为"SATA"、"PCI-E"、“NVMe”，如果UseSSD为true ，则必选 |No|
| **InstanceMode** | string | UDB实例模式类型, 可选值如下: "Normal": 普通版UDB实例 "HA": 高可用版UDB实例 默认是"Normal" |No|
| **UDBCId** | string | 专区ID信息（如果这个参数存在这说明是在专区中创建DB） |No|
| **CPU** | int | cpu核数 |No|
| **InstanceType** | string | UDB数据库机型: "Normal": "标准机型" , "SATA_SSD": "SSD机型" , "PCIE_SSD": "SSD高性能机型" , "Normal_Volume": "标准大容量机型", "SATA_SSD_Volume": "SSD大容量机型" , "PCIE_SSD_Volume": "SSD高性能大容量机型", "NVMe_SSD": "快杰机型" |No|
| **BackupZone** | string | 跨可用区高可用备库所在可用区，参见 [可用区列表](api/summary/regionlist) |No|
| **SubnetId** | string | 子网ID |No|
| **VPCId** | string | VPC的ID |No|
| **DisableSemisync** | boolean | 是否开启异步高可用，默认不填，可置为true |No|
| **ClusterRole** | string | 当DB类型(DBTypeId)为mongodb时，需要指定mongo的角色，可选值为<br />configsrv (配置节点)，shardsrv (数据节点) |No|
| **HAArch** | string | 高可用架构:<br />1） haproxy（默认）: 当前仅支持mysql。<br />2） sentinel: 基于vip和哨兵节点的架构，当前支持mysql和pg。 |No|
| **Tag** | string | 实例所在的业务组名称 |No|
| **EnableIpV6** | boolean | 是否创建使用ipv6 资源， 默认为false， 或者不填， 创建ipv6为true |No|
| **CouponId** | string | 使用的代金券id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DBId** | string | BD实例id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUDBInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&DBTypeId=mysql-5.6
&ChargeType=Month   
&Name=my_test_udb
&AdminUser=root
&AdminPassword=mysql_12
&Port=3306
&ParamGroupId=10
&MemoryLimit=1500
&DiskSpace=200
&InstanceMode=HA
&ClusterRole=IcPiHioG
&HAArch=haproxy
&Tag=awpGFPaP
&EnableIpV6=true
```

### 响应示例
    
```json
{
  "Action": "CreateUDBInstanceResponse",
  "DBId": "udbha-xxxxxx",
  "RetCode": 0
}
```





