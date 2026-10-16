# 创建预检查任务 - CreateUDTSPrecheckTask

## 简介

创建预检查任务






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDTSPrecheckTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Type** | string | 任务类型，唯一值：transfer(数据传输) |**Yes**|
| **Source.N.Mode** | string | 任务模式，值可以是 full, incremental, full+incremental, bidirectional |**Yes**|
| **Source.N.DataType** | string | 数据库类型，比如 mysql |**Yes**|
| **Source.N.NWType** | string | 源网络类型，可以是 public,user,dedicated_line |**Yes**|
| **Source.N.ServiceType** | string | 服务类型，值可以是small/medium/large/2xlarge/4xlarge |**Yes**|
| **Source.N.BandwidthLimit** | string | 源端限速值，单位为 MB/s |No|
| **Source.N.MySQLNode.Host** | string | MySQL 源数据库地址 |No|
| **Source.N.MySQLNode.Port** | string | MySQL 源数据库端口 |No|
| **Source.N.MySQLNode.User** | string | MySQL 源数据库用户名 |No|
| **Source.N.MySQLNode.Password** | string | MySQL 源数据库密码 |No|
| **Source.N.MySQLNode.VPCId** | string | MySQL 源数据库 VPC ID，当网络类型为 user 时需要填写 |No|
| **Source.N.MySQLNode.SubnetId** | string | MySQL 源数据库子网 ID，当网络类型为 user 时需要填写， |No|
| **Source.N.MySQLNode.DataRegion** | string | MySQL 数据库地域，比如 cn-bj2 |No|
| **Source.N.MySQLNode.Database** | string | MySQL 需要迁移的 DB 名称 |No|
| **Source.N.MySQLNode.Table** | string | MySQL 需要迁移的 table 名 |No|
| **Target.DataType** | string | 目标数据库类型，比如 mysql |**Yes**|
| **Target.NWType** | string | 目标 db 网络类型，目前仅支持 user |**Yes**|
| **Target.BandwidthLimit** | string | 目标端限速，单位为 MB/s |No|
| **Target.MySQLNode.Host** | string | MySQL 目标数据库地址， 比如 10.9.37.212 |No|
| **Target.MySQLNode.Port** | string | MySQL 目标数据库端口，比如 3306 |No|
| **Target.MySQLNode.User** | string | MySQL 目标数据库用户名，比如 root |No|
| **Target.MySQLNode.Password** | string | MySQL 目标数据库密码 |No|
| **Target.MySQLNode.VPCId** | string | MySQL 目标数据库 VPC,比如 uvnet-1wz5rqte |No|
| **Target.MySQLNode.SubnetId** | string | MySQL 目标数据库子网 ID ,比如 subnet-zl44fktq |No|
| **Target.MySQLNode.DataRegion** | string | MySQL 目标数据库地域，比如 cn-bj2 |No|
| **Target.MySQLNode.NoBinlog** | string | MySQL 是否在全量过程中，临时禁用目标 MySQL 产生 binlog，在目标磁盘空间不足，或者需要获取更快的迁移速度时可以使用，该参数会破坏目标 MySQL 的高可用 |No|
| **Name** | string | task 名称，长度不能超过 128 |No|
| **MaxRetryCount** | string | 重试次数，最大为 5。 默认为0 |No|
| **Remark** | string | 备注信息，长度不能大于 255 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TaskID** | array[string] | 预检查任务ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUDTSPrecheckTask
&ProjectId=ntXNtkID
&Type=AfoZJduy
&Source=IHEAqmdk
&Target=aBkkoVUT
&Name=TxOYjfgR
&MaxRetryCount=BPRbxxan
&Query=NbKDegKu
&Source.N.DataType=NNZyJdsV
&Source.N.NWType=qCxNICZB
&Target.DataType=YRCqYYvh
&Target.NWType=oaxpZkwo
&Source.N.ServiceType=MxwpRHJs
&Remark=AFDheYLi
&Source.N.BandwidthLimit=UNLVDJSa
&Source.N.MySQLNode.Host=HwaxGCXx
&Source.N.MySQLNode.Port=NHcFDODf
&Source.N.MySQLNode.User=ULywglVp
&Source.N.MySQLNode.Password=qbgJLOXF
&Source.N.MySQLNode.VPCId=BXdJnCHC
&Source.N.MySQLNode.SubnetId=XqeTEjRE
&Source.N.MySQLNode.DataRegion=LQxgOTGW
&Source.N.MySQLNode.Database=BsDfdZtc
&Source.N.MySQLNode.Table=KxFFerIx
&Target.BandwidthLimit=thOJfkpI
&Target.MySQLNode.Host=JZSOqdFp
&Target.MySQLNode.Port=nSWwqTBX
&Target.MySQLNode.User=WnQjwEdM
&Target.MySQLNode.Password=DgVchQcK
&Target.MySQLNode.VPCId=dpfwwKZF
&Target.MySQLNode.SubnetId=MiLTnWyz
&Target.MySQLNode.DataRegion=ecSjgaPM
&Target.MySQLNode.NoBinlog=biLinsqJ
```

### 响应示例
    
```json
{
  "Action": "CreateUDTSPrecheckTaskResponse",
  "Data": {},
  "Message": "TVBFmuIU",
  "RetCode": 0
}
```





