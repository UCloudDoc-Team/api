# 创建SQLServer数据库 - CreateUDBSQLServerInstance

## 简介

创建UDB实例（包括创建SQLServer实例以及从备份恢复实例）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUDBSQLServerInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDBSQLServerInstance`                        | **Yes** |
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
| **DBTypeId** | string | DB类型，SQL Server按版本细分 sqlserver-2017、sqlserver-2019、sqlserver-2022 |**Yes**|
| **Port** | int | 端口号，sqlserver默认1433 |**Yes**|
| **DiskSpace** | int | 磁盘空间(GB), 暂时支持20G - 32T |**Yes**|
| **StorageClass** | string | 存储类型 CLOUD_RSSD: RSSD 云盘，该字段和SpecificationClass组合使用，CLOUD_RSSD对应O型<br /> |**Yes**|
| **SpecificationClass** | string | 规格类型 O: NVMe型 |**Yes**|
| **InstanceMode** | string | UDB实例模式类型, 可选值如下: "Normal": SQL Server普通版实例 "HA": SQL Server集群版实例 默认是"Normal" |No|
| **MachineType** | string | 规格类型 ID，如果创建的是SQL Server集群版，该参数必填，请通过 ListUDBMachineType 接口获取，返回体中的ID字段为MachineType的值。 |No|
| **CPU** | int | CPU核，如果是创建的SQL Server普通版，该参数必传，目前支持2/4/8/16/32/64 |No|
| **MemoryLimit** | int | 内存限制(MB)，如果是创建的SQL Server普通版，该参数必传，目前支持以下几档 2000M/4000M/ 6000M/8000M/12000M/16000M/ 24000M/32000M/48000M/ 64000M/96000M/128000M/192000M/256000M/320000M |No|
| **ChargeType** | string | Year， Month， Dynamic，Trial，默认: Month |No|
| **Quantity** | int | 购买时长，默认值1 |No|
| **BackupCount** | int | 备份策略，每周备份数量，默认7次 |No|
| **BackupTime** | int | 备份策略，备份开始时间，单位小时计，默认1点 |No|
| **BackupDuration** | int | 备份策略，备份时间间隔，单位小时计，默认24小时 |No|
| **BackupId** | int | 备份id，如果指定，则表明从备份恢复实例 |No|
| **SubnetId** | string | 子网ID，如果创建的是SQL Server集群版，该参数必填 |No|
| **VPCId** | string | VPC的ID，如果创建的是SQL Server集群版，该参数必填 |No|
| **Tag** | string | 实例所在的业务组名称 |No|
| **AlarmTemplateId** | string | 告警模版id |No|
| **BackupURL** | string | 备份文件的US3内网下载地址 |No|
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
https://api.ucloud.cn/?Action=CreateUDBSQLServerInstance
&Region=THJIyXyN
&Zone=HpQHnozE
&ProjectId=JwqIWIjj
&Name=rNOYPBTC
&AdminPassword=acSNMykE
&DBTypeId=mysql-5.7
&Port=3
&DiskSpace=4
&ParamGroupId=8
&MachineType=gdpKaOtO
&StorageClass=Tkhljajo
&SpecificationClass=iNOoQCIy
&ChargeType=DJqyTZGn
&Quantity=1
&AdminUser=iubRWVqD
&BackupCount=5
&BackupTime=9
&BackupDuration=2
&BackupId=6
&InstanceMode=Normal
&BackupZone=dmAAHDqi
&SubnetId=cZaRQtYC
&VPCId=bQvoecEs
&DisableSemisync=true
&Tag=KfBCfAdq
&DBSubVersion=8.0.16
&CaseSensitivityParam=6
&AlarmTemplateId=QxdZCPNH
&BackupURL=YcGkCMuV
&SemisyncFlag=6
&Labels.N.Key=xJDsbtDA
&Labels.N.Value=yJvmSRtF
&CouponId=HrvDLXeG
&CPU=2
&MemoryLimit=4
&CPU=1
&MemoryLimit=6
&CPU=4
&MemoryLimit=2
&CPU=4
&MemoryLimit=4
&CPU=9
&MemoryLimit=6
&CPU=2
&MemoryLimit=3
```

### 响应示例
    
```json
{
  "Action": "CreateUDBSQLServerInstanceResponse",
  "DBId": "RLaoBEzT",
  "RetCode": 0
}
```





