# 检查任务 - CheckUDTSTask

## 简介

对UDTS 任务提供预检查功能






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CheckUDTSTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | task 名称，长度不能超过 128 |**Yes**|
| **Type** | string | 任务类型，值为 transfer 或 integration， transfer 时任务为 数据迁移，integration 时任务为 数据集成。 |**Yes**|
| **MaxRetryCount** | string | 重试次数，最大为 5。 默认为0 |**Yes**|
| **Query** | string | 废弃 |No|
| **Source.N.Mode** | string | // 任务类型，值可以是 full, incremental, full+incremental, bidirectional |No|
| **Source.N.DataType** | string | 数据库类型 |No|
| **Source.N.NWType** | string | 源网络类型，可以是 public,user,dedicated_line |No|
| **Source.N.MySQLNode.Host** | string | 源数据库地址， 比如 10.9.37.200 |No|
| **Source.N.MySQLNode.Port** | int | 源 MySQL 端口，如 3306 |No|
| **Source.N.MySQLNode.User** | string | 源 MySQL 用户名，如 root |No|
| **Source.N.MySQLNode.Password** | string | 源 MySQL 密码 |No|
| **Source.N.MySQLNode.VPCId** | string | VPC |No|
| **Source.N.MySQLNode.SubnetId** | string | 子网 ID |No|
| **Source.N.MySQLNode.DataRegion** | string | 数据库地域，比如 cn-bj2 |No|
| **Source.N.MySQLNode.Database** | string | 需要迁移的 DB 名称 |No|
| **Source.N.MySQLNode.Table** | string | 需要迁移的 table 名 |No|
| **Source.N.MySQLNode.SyncData.BinlogName** | string | 增量时需要指定的 binlog name，可以通过 show master status 获取，或者全量+增量任务会自动设置 |No|
| **Source.N.MySQLNode.SyncData.BinlogPos** | int | 增量时需要指定的 binlog pos，可以通过 show master status 获取，或者全量+增量任务会自动设置 |No|
| **Source.N.MySQLNode.SyncData.ServerID** | int | 增量时需要指定的 serverID，不能和现有的 slave 重复，预检查时会检查该值 |No|
| **Source.N.MySQLNode.SyncData.BinlogGTID** | string | 增量时需要指定的 binlog gtid，可以通过 show master status 获取，或者全量+增量任务会自动设置 |No|
| **QueryData.N.DBName** | string | 数据集成时需要迁移的 DB 名 |No|
| **QueryData.N.NewDBName** | string | 数据集成时迁移后的 DB 名 |No|
| **Target.DataType** | string | 目标数据库类型，比如 mysql |No|
| **Target.NWType** | string | 目标 db 网络类型，目前进支持 user |No|
| **Target.MySQLNode.Host** | string | 目标数据库地址， 比如 10.9.37.212 |No|
| **Target.MySQLNode.Port** | int | 目标数据库端口，比如 3306 |No|
| **Target.MySQLNode.User** | string | 目标数据库用户名，比如 root |No|
| **Target.MySQLNode.Password** | string | 目标数据库密码 |No|
| **Target.MySQLNode.VPCId** | string | 目标数据库 VPC,比如 uvnet-1wz5rqte |No|
| **Target.MySQLNode.SubnetId** | string | 目标数据库子网 ID ,比如 subnet-zl44fktq |No|
| **Target.MySQLNode.DataRegion** | string | 目标数据库地域，比如 cn-bj2 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*CheckUDTSTaskResult*](#CheckUDTSTaskResult) | 检查结果 |**Yes**|

#### 数据模型


#### CheckUDTSTaskResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Source** | [*CheckResult*](#CheckResult) |  |No|
| **Target** | [*CheckResult*](#CheckResult) |  |No|

#### CheckResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Config** | [*CheckResultItem*](#CheckResultItem) |  |No|
| **Connection** | [*CheckResultItem*](#CheckResultItem) |  |No|
| **Privileges** | [*CheckResultItem*](#CheckResultItem) |  |No|

#### CheckResultItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **State** | string | 状态 |**Yes**|
| **ErrMessage** | string |  |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CheckUDTSTask
&ProjectId=ySxOuFNP
&Name=iybJMhOY
&Type=kKLbtCIE
&Source=WQVyJAPj
&Target=ELyCuYTU
&MaxRetryCount=ozdxEUIr
&Query=PizEAjrP
&Source.N.Mode=PzcXhLrG
&Source.N.DataType=bZWssMSz
&Source.N.NWType=QTIhWJAT
&Source.N.MySQLNode.Host=tYybGVwL
&Source.N.MySQLNode.Port=2
&Source.N.MySQLNode.User=IVvsQESS
&Source.N.MySQLNode.Password=rehIyiiG
&Source.N.MySQLNode.VPCId=oslSTCGw
&Source.N.MySQLNode.SubnetId=knkzvAuv
&Source.N.MySQLNode.DataRegion=BsDfVJsM
&Source.N.MySQLNode.Database=ICfGrSzd
&Source.N.MySQLNode.Table=sSYUlfrC
&Source.N.MySQLNode.SyncData.BinlogName=aUVlvMba
&Source.N.MySQLNode.SyncData.BinlogPos=9
&Source.N.MySQLNode.SyncData.ServerID=9
&Source.N.MySQLNode.SyncData.BinlogGTID=ZfHgMkbW
&Source.N.MySQLNode.QueryData.N.DBName=AXGkZnMf
&Source.N.MySQLNode.QueryData.N.NewDBName=hGUvPTmf
&Target.DataType=vcFAMLPD
&Target.NWType=ttJRgGYj
&Target.MySQLNode.Host=UJQuSQBf
&Target.MySQLNode.Port=4
&Target.MySQLNode.User=FzrvgBcz
&Target.MySQLNode.Password=LbAmOPmz
&Target.MySQLNode.VPCId=kFiSKqpB
&Target.MySQLNode.SubnetId=VTTYIvGY
&Target.MySQLNode.DataRegion=MzdqBMqb
```

### 响应示例
    
```json
{
  "Action": "CheckUDTSTaskResponse",
  "Data": {},
  "Message": "aKSpQMwy",
  "RetCode": 0
}
```





