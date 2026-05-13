# 创建MySQL数据库 - CreateUDBMySQLInstance

## 简介

创建UDB实例（包括创建mysql NVMe、共享型和O2实例以及从备份恢复实例）

?> 创建跨可用区的高可用注意项:<br />1. 需要参数 BackupZone：值为高可用容灾的ZoneId<br />2. 参数ParamGroupId: 值为跨可用区的配置文件，可以通过DescribeUDBParamGroup获得




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUDBMySQLInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDBMySQLInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 实例名称，至少6位 |**Yes**|
| **AdminPassword** | string | 管理员密码 |**Yes**|
| **DBTypeId** | string | DB类型，mysql按版本细分 mysql-8.4, mysql-8.0,  mysql-5.7, percona-5.7, mysql-5.6, percona-5.6、mysql-5.5 |**Yes**|
| **Port** | int | 端口号，mysql默认3306 |**Yes**|
| **DiskSpace** | int | 磁盘空间(GB), 暂时支持20G - 32T |**Yes**|
| **ParamGroupId** | int | DB实例使用的配置参数组id |**Yes**|
| **MachineType** | string | 规格类型 ID，请通过 ListUDBMachineType 接口获取，返回体中的ID字段为MachineType的值。 |**Yes**|
| **StorageClass** | string | 存储类型 CLOUD_RSSD: RSSD 云盘， CLOUD_SSD_ESSENTIAL: SSD Essential云盘 ，该字段和SpecificationClass组合使用，CLOUD_RSSD对应O型，CLOUD_SSD_ESSENTIAL对应OM型(北京2、乌兰察布支持)，注：圣保罗、丹佛、哈萨克斯坦地域仅支持O2机型，CLOUD_RSSD对应O2型<br /> |**Yes**|
| **SpecificationClass** | string | 规格类型 O: NVMe型, O2: O2 ,OM: 共享型 |**Yes**|
| **ChargeType** | string | Year， Month， Dynamic，Trial，默认: Month |No|
| **Quantity** | int | 购买时长，默认值1 |No|
| **BackupCount** | int | 备份策略，每周备份数量，默认7次 |No|
| **BackupTime** | int | 备份策略，备份开始时间，单位小时计，默认1点 |No|
| **BackupDuration** | int | 备份策略，备份时间间隔，单位小时计，默认24小时 |No|
| **BackupId** | int | 备份id，如果指定，则表明从备份恢复实例 |No|
| **InstanceMode** | string | UDB实例模式类型, 可选值如下: "Normal": 普通版UDB实例 "HA": 高可用版UDB实例 默认是"Normal" |No|
| **BackupZone** | string | 跨可用区高可用备库所在可用区，参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **SubnetId** | string | 子网ID |No|
| **VPCId** | string | VPC的ID |No|
| **DisableSemisync** | boolean | 是否开启异步高可用，默认不填，可置为true |No|
| **Tag** | string | 实例所在的业务组名称 |No|
| **DBSubVersion** | string | MySQL 小版本号，支持指定小版本进行创建，请通过 DescribeUDBType 接口获取可用版本。 |No|
| **CaseSensitivityParam** | int | mysql大小写参数, 0 为大小写敏感, 1 为大小写不敏感, 目前只针对mysql8.0有效 |No|
| **AlarmTemplateId** | string | 告警模版id |No|
| **BackupURL** | string | 备份文件的US3内网下载地址 |No|
| **SemisyncFlag** | int | 半同步开启开关 1：表示开启半同步，2：表示关闭半同步，0：表示默认值，默认也是开启半同步 |No|
| **Labels.N.Key** | string | 用户资源标签的键值 |No|
| **Labels.N.Value** | string | 用户资源标签值 |No|
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
https://api.ucloud.cn/?Action=CreateUDBMySQLInstance
&Region=DHSQjnMH
&Zone=VPbfMFgr
&ProjectId=QqMPIElo
&Name=VJRdgjLz
&AdminPassword=qpuNzHWu
&DBTypeId=mysql-5.7
&Port=1
&DiskSpace=2
&ParamGroupId=1
&SpecificationType=BSzvvsmr
&MachineType=vVzRuiXW
&StorageClass=iFbCPKNS
&SpecificationClass=VyvAhzBv
&ChargeType=fBuCAPrS
&Quantity=7
&AdminUser=BrxrNMhG
&BackupCount=8
&BackupTime=6
&BackupDuration=5
&BackupId=8
&InstanceMode=Normal
&BackupZone=rFyctFJb
&SubnetId=daZLUdLl
&VPCId=hHzobfnk
&DisableSemisync=true
&Tag=fEWwwrJs
&DBSubVersion=8.0.16
&CaseSensitivityParam=6
&AlarmTemplateId=msYGzxTY
&BackupURL=jbeGhHuy
&SemisyncFlag=3
&Labels.N.Key=ZSDypLJv
&Labels.N.Value=VZexUEuN
&CouponId=XasoJFsT
```

### 响应示例
    
```json
{
  "Action": "CreateUDBMySQLInstanceResponse",
  "DBId": "JhdlRKKq",
  "RetCode": 0
}
```





