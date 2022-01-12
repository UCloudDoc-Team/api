# 创建UDTS任务 - CreateUDTSTask

## 简介

创建UDTS任务






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUDTSTask`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 任务名称，长度不能超过 128 |**Yes**|
| **Type** | string | 任务类型，transfer(数据传输) 或 integration(数据集成) |**Yes**|
| **Source.N.Mode** | string | 任务模式，值可以是 full, incremental, full+incremental, bidirectional |**Yes**|
| **Source.N.DataType** | string | 数据库类型，比如 mysql |**Yes**|
| **Source.N.NWType** | string | 源网络类型，可以是 public,user,dedicated_line |**Yes**|
| **Source.N.ServiceType** | string | 服务类型，值可以是small、medium、large，分别对应“基础版”、“轻量版”和“旗舰版” |**Yes**|
| **Source.N.BandwidthLimit** | int | 源端限速值，单位为  MB/s |No|
| **Source.N.MySQLNode.Host** | string | 源数据库地址 |No|
| **Source.N.MySQLNode.Port** | int | 源数据库端口 |No|
| **Source.N.MySQLNode.User** | string | 源数据库用户名 |No|
| **Source.N.MySQLNode.Password** | string | 源数据库密码 |No|
| **Source.N.MySQLNode.VPCId** | string | 源数据库 VPC ID，当网络类型为 user 时需要填写，可以从 https://console.ucloud.cn/vpc/vpc 获取，比如 uvnet-u0ecace |No|
| **Source.N.MySQLNode.SubnetId** | string | 源数据库子网 ID，当网络类型为 user 时需要填写，可以从 https://console.ucloud.cn/vpc/subnet，比如 subnet-2sloxs |No|
| **Source.N.MySQLNode.DataRegion** | string | 数据库地域，比如 cn-bj2 |No|
| **Source.N.MySQLNode.Database** | string | 需要迁移的 DB 名称 |No|
| **Source.N.MySQLNode.Table** | string | 需要迁移的 table 名 |No|
| **Source.N.MySQLNode.SyncData.BinlogName** | string | 增量时需要指定的 binlog name，可以通过 show master status 获取，或者全量+增量任务会自动设置 |No|
| **Source.N.MySQLNode.SyncData.BinlogPos** | int | 增量时需要指定的 binlog pos，可以通过 show master status 获取，或者全量+增量任务会自动设置 |No|
| **Source.N.MySQLNode.SyncData.ServerID** | int | 增量时需要指定的 serverID，不能和现有的 slave 重复，预检查时会检查该值 |No|
| **Source.N.MySQLNode.SyncData.BinlogGTID** | string | 增量时需要指定的 binlog gtid，可以通过 show master status 获取，或者全量+增量任务会自动设置 |No|
| **QueryData.N.DBName** | string | 数据集成时需要迁移的 DB 名 |No|
| **QueryData.N.NewDBName** | string | 数据集成时迁移后的 DB 名 |No|
| **QueryData.N.TableData.TableNames** | string | 暂时未使用该字段 |No|
| **QueryData.N.TableData.ExcludeTables** | boolean | 暂时未使用该字段 |No|
| **TableMaps.N.TableName** | string | 数据集成时需要迁移的 Table 名 |No|
| **TableMaps.N.NewTableName** | string | 数据集成时迁移后的 Table 名 |No|
| **Source.N.MySQLNode.KeepExistData** | boolean | 是否保留原有数据，只有数据集成时该参数才有效 |No|
| **Source.N.MySQLNode.DupAction** | string | 重复数据处理规则，数据集成时该参数才有效，值为 ignore或者replace |No|
| **Source.N.MySQLNode.SSLSecurity.SSLCA** | string | ca 证书，目前仅支持 pem 格式; 需要将文件内容 base64 |No|
| **Source.N.MySQLNode.SSLSecurity.SSLCert** | string | 客户端证书; 需要将文件内容 base64   |No|
| **Source.N.MySQLNode.SSLSecurity.SSLKey** | string | 客户端私钥， 需要将文件内容 base64   |No|
| **Target.Mode** | string |  |**Yes**|
| **Target.DataType** | string | 目标数据库类型，比如 mysql |**Yes**|
| **Target.NWType** | string | 目标 db 网络类型，目前仅支持 user |**Yes**|
| **Target.BandwidthLimit** | string | 目标端限速，单位为 MB/s |No|
| **Target.MySQLNode.Host** | string | 目标数据库地址， 比如 10.9.37.212 |No|
| **Target.MySQLNode.Port** | int | 目标数据库端口，比如 3306 |No|
| **Target.MySQLNode.User** | string | 目标数据库用户名，比如 root |No|
| **Target.MySQLNode.Password** | string | 目标数据库密码 |No|
| **Target.MySQLNode.VPCId** | string | 目标数据库 VPC,比如 uvnet-1wz5rqte |No|
| **Target.MySQLNode.SubnetId** | string | 目标数据库子网 ID ,比如 subnet-zl44fktq |No|
| **Target.MySQLNode.DataRegion** | string | 目标数据库地域，比如 cn-bj2 |No|
| **Target.MySQLNode.NoBinlog** | boolean | 是否在全量过程中，临时禁用目标 MySQL 产生 binlog，在目标磁盘空间不足，或者需要获取更快的迁移速度时可以使用，该参数会破坏目标 MySQL 的高可用 |No|
| **MaxRetryCount** | string | 重试次数，最大为 5。 默认为0 |No|
| **Query** | string | 暂时未使用该字段 |No|
| **IsUnidirection** | string | 暂时未使用该字段 |No|
| **Remark** | string | 备注信息，长度不能大于 255 |No|
| **Quantity** | int | 购买时长, 默认: 1 |No|
| **ChargeType** | string | 付费方式, 枚举值为: Year, 按年付费; Month, 按月付费；Dynamic, 按需付费(需开启权限)；默认为按月付费 |No|
| **CouponId** | string | 代金券ID, 默认不使用 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | object |  |**Yes**|
| **TaskId** | string | 任务ID，目前用于控制台操作日志 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUDTSTask
&Region=cn-zj
&ProjectId=RxjtEuje
&Name=AxfpqbHf
&Type=LSwCQRth
&Source=DmzCcRiT
&Target=PIVlSiCd
&MaxRetryCount=iPgQdCJm
&Query=YqlCGHLR
&IsDedicatedLine=false
&IsUnidirection=NYPZcshe
&Source.N.Mode=fWsqXqqm
&Source.N.DataType=TGmlMgtA
&Source.N.MySQLNode.Host=nTEGdKOV
&Source.N.MySQLNode.Port=9
&Source.N.MySQLNode.User=PPPsDLEy
&Source.N.MySQLNode.Password=UEEuSVpz
&Source.N.MySQLNode.VPCId=RbLzaWDM
&Source.N.MySQLNode.SubnetId=sHQsachY
&Source.N.MySQLNode.DataRegion=jQPRqZAQ
&Source.N.MySQLNode.Database=HvYuzdTY
&Source.N.MySQLNode.Table=ikPDQCrF
&Source.N.MySQLNode.SyncData.BinlogName=VSbjNbof
&Source.N.MySQLNode.SyncData.BinlogPos=FpQadMWc
&Source.N.MySQLNode.SyncData.ServerID=vcgeBxiE
&Source.N.MySQLNode.SyncData.BinlogGTID=zLehFoxC
&Remark=EtIKkkRF
&Source.N.Mode=uDwvRgXl
&Source.N.DataType=DbBEiBzx
&Source.N.MySQLNode.Host=QCuymrrw
&Source.N.MySQLNode.Port=4
&Source.N.MySQLNode.User=MarpaRLp
&Source.N.MySQLNode.Password=qdYuFUQV
&Source.N.MySQLNode.VPCId=jNXsoOuw
&Source.N.MySQLNode.SubnetId=ZckYkcsB
&Source.N.MySQLNode.DataRegion=hNFUVoFD
&Source.N.MySQLNode.Database=paqulSIo
&Source.N.MySQLNode.Table=LevJUVpc
&Source.N.MySQLNode.SyncData.BinlogName=yWEMtwth
&Source.N.MySQLNode.SyncData.BinlogPos=4
&Source.N.MySQLNode.SyncData.ServerID=7
&Source.N.MySQLNode.SyncData.BinlogGTID=tkPozizE
&Source.N.MySQLNode.QueryData.N.DBName=PmTlGFxe
&Source.N.MySQLNode.QueryData.N.NewDBName=AuKmDOWG
&Source.N.MySQLNode.QueryData.N.TableData.TableNames=YOqUXbCU
&Source.N.MySQLNode.QueryData.N.TableData.ExcludeTables=false
&Source.N.MySQLNode.QueryData.N.TableMaps.N.TableName=TkNweIYw
&Source.N.MySQLNode.QueryData.N.TableMaps.N.NewTableName=Rkpkgosy
&Source.N.MySQLNode.KeepExistData=false
&Source.N.MySQLNode.DupAction=kNJFnpEk
&Source.N.MySQLNode.NoBinlog=lBRXNtLr
&Remark=EdjTSZqb
&Source.N.Mode=GCHwvAzt
&Source.N.DataType=KgnzrHgW
&Source.N.MySQLNode.Host=eqKqgEch
&Source.N.MySQLNode.Port=3
&Source.N.MySQLNode.User=SkPjrFne
&Source.N.MySQLNode.Password=kXgeJFVs
&Source.N.MySQLNode.VPCId=wKnpHJUL
&Source.N.MySQLNode.SubnetId=EDvTEptA
&Source.N.MySQLNode.DataRegion=UbTExpri
&Source.N.MySQLNode.Database=kbThgUPN
&Source.N.MySQLNode.Table=kUhnQaHD
&Source.N.MySQLNode.SyncData.BinlogName=ucmFxWqu
&Source.N.MySQLNode.SyncData.BinlogPos=8
&Source.N.MySQLNode.SyncData.ServerID=1
&Source.N.MySQLNode.SyncData.BinlogGTID=vmQUWAso
&Source.N.MySQLNode.QueryData.N.DBName=TjzHlKBS
&Source.N.MySQLNode.QueryData.N.NewDBName=wveCIOeo
&Source.N.MySQLNode.QueryData.N.TableData.TableNames=ZLNqouij
&Source.N.MySQLNode.QueryData.N.TableData.ExcludeTables=false
&Source.N.MySQLNode.QueryData.N.TableMaps.N.TableName=dukuiUfI
&Source.N.MySQLNode.QueryData.N.TableMaps.N.NewTableName=bpOzaOOY
&Source.N.MySQLNode.KeepExistData=true
&Source.N.MySQLNode.DupAction=qpKOxddJ
&Source.N.MySQLNode.NoBinlog=ZmIFChsZ
&Target.Mode=RboYuTfl
&Target.DataType=lGvNkvQC
&Target.MySQLNode.Host=WHsxlqhF
&Target.MySQLNode.Port=9
&Target.MySQLNode.User=fqccASPj
&Target.MySQLNode.Password=aiOFwckd
&Target.MySQLNode.VPCId=eCxGDRjy
&Target.MySQLNode.SubnetId=KTYviHnO
&Target.MySQLNode.DataRegion=JAJjVkwt
&Remark=LqITzTWH
&Source.N.Mode=MeuRHalq
&Source.N.DataType=HGtXznTH
&Source.N.MySQLNode.Host=MXzVlABy
&Source.N.MySQLNode.Port=6
&Source.N.MySQLNode.User=VkFlnvFJ
&Source.N.MySQLNode.Password=cZsjBPEN
&Source.N.MySQLNode.VPCId=yhseMSjn
&Source.N.MySQLNode.SubnetId=vzigyOkC
&Source.N.MySQLNode.DataRegion=GNfKXekt
&Source.N.MySQLNode.Database=VDYbUHJz
&Source.N.MySQLNode.Table=HPoGAdzN
&Source.N.MySQLNode.SyncData.BinlogName=WnhzlWBW
&Source.N.MySQLNode.SyncData.BinlogPos=6
&Source.N.MySQLNode.SyncData.ServerID=5
&Source.N.MySQLNode.SyncData.BinlogGTID=dgpWMwNV
&Source.N.MySQLNode.QueryData.N.DBName=tVfORnwW
&Source.N.MySQLNode.QueryData.N.NewDBName=kATgswhS
&Source.N.MySQLNode.QueryData.N.TableData.TableNames=SRIMxFtx
&Source.N.MySQLNode.QueryData.N.TableData.ExcludeTables=true
&Source.N.MySQLNode.QueryData.N.TableMaps.N.TableName=WBnoOVha
&Source.N.MySQLNode.QueryData.N.TableMaps.N.NewTableName=tNKMGxTU
&Source.N.MySQLNode.KeepExistData=true
&Source.N.MySQLNode.DupAction=QjlOgJIR
&Source.N.MySQLNode.NoBinlog=UNQtIBlq
&Target.Mode=bxjaBkue
&Target.DataType=rxOuZsXz
&Target.MySQLNode.Host=uCNhKVcq
&Target.MySQLNode.Port=8
&Target.MySQLNode.User=SQvUtfEt
&Target.MySQLNode.Password=mFtYsBCO
&Target.MySQLNode.VPCId=mbxEJZpE
&Target.MySQLNode.SubnetId=hLGVVyoA
&Target.MySQLNode.DataRegion=DzsvzZZo
&Source.N.NWType=yGuzFPDP
&Source.N.BandwidthLimit=6
&Target.NWType=AdfJzmEz
&Target.BandwidthLimit=CFGpkzid
&Source.N.MySQLNode.SSLSecurity.SSLCA=MQKwVQcF
&Source.N.MySQLNode.SSLSecurity.SSLCert=yrUzEnuZ
&Source.N.MySQLNode.SSLSecurity.SSLKey=OYuQESyM
&Source.N.ServiceType=vVuYpUaV
&Quantity=4
&ChargeType=diYSAAQT
&CouponId=flfTnXPG
```

### 响应示例
    
```json
{
  "Action": "CreateUDTSTaskResponse",
  "Data": {},
  "Message": "FnZvjDcL",
  "RetCode": 0,
  "TaskID": "zJeiMttl"
}
```





