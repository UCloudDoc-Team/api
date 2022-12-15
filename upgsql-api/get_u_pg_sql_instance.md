# 获取云数据库实例描述 - GetUPgSQLInstance

## 简介

获取PG云数据库实例描述






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUPgSQLInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUPgSQLInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **InstanceID** | string | 资源ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | [*UDBInstance*](#UDBInstance) |  |**Yes**|

#### 数据模型


#### UDBInstance

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Zone** | string | DB实例所在可用区 |No|
| **BackupZone** | string | 跨可用区高可用备库所在可用区 |No|
| **InstanceID** | string | DB实例id |No|
| **Name** | string | 实例名称 |No|
| **DBVersion** | string | DB 版本 |No|
| **ParamGroupID** | int | DB实例使用的配置参数组id |No|
| **AdminUser** | string | 管理员帐户名，默认root |No|
| **IP** | string | DBip |No|
| **Port** | int | DB port |No|
| **VPCID** | string | VPC的ID |No|
| **SubnetID** | string | 子网ID |No|
| **Remark** | string | 备注 |No|
| **BackupCount** | int | 备份文件保留的数量，默认7次 |No|
| **BackupBeginTime** | int | 备份开始时间，单位小时计，默认3点 |No|
| **BackupTimeRange** | int | 备份的时间段，范围[0,23] |No|
| **BackupDate** | string | 用于设置备份策略的备份日期标记位。共7位,每一位为一周中一天的备份情况 0表示关闭当天备份,1表示打开当天备份。最右边的一位 为星期天的备份开关，其余从右到左依次为星期一到星期 六的备份配置开关，每周必须至少设置两天备份。 例如：1100000 表示打开星期六和星期五的自动备份功能 |No|
| **State** | string | DB状态标记 Init：初始化中，Fail：安装失败，Starting：启动中，Running：运行，Shutdown：关闭中，Shutoff：已关闭，Delete：已删除，Upgrading：升级中，Promoting：提升为独库进行中，Recovering：恢复中，Recover fail：恢复失败 |No|
| **CreateTime** | int | DB实例创建时间，采用UTC计时时间戳 |No|
| **ModifyTime** | int | DB实例修改时间，采用UTC计时时间戳 |No|
| **ExpiredTime** | int | DB实例过期时间，采用UTC计时时间戳 |No|
| **MemoryLimit** | int | 内存限制(MB)，默认根据配置机型 |No|
| **DiskSpace** | int | 磁盘空间(GB), 默认根据配置机型 |No|
| **DiskUsedSize** | float | DB实例磁盘已使用空间，单位GB |No|
| **DataFileSize** | float | DB实例数据文件大小，单位GB |No|
| **SystemFileSize** | float | DB实例系统文件大小，单位GB |No|
| **LogFileSize** | float | DB实例日志文件大小，单位GB |No|
| **InstanceMode** | string | Normal/HA,普通/高可用 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUPgSQLInstance
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=NmpXWjBt
&InstanceID=zercJTxf
```

### 响应示例
    
```json
{
  "Action": "GetUPgSQLInstanceResponse",
  "DataSet": {},
  "Message": "BTbgDWAl",
  "RetCode": 0
}
```





