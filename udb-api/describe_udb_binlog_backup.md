# 列表UDB实例Binlog自动备份信息 - DescribeUDBBinlogBackup

## 简介

列表UDB实例Binlog自动备份信息

?> 不支持新版（NVMe型）MongoDB/PostgreSQL， 新版（NVMe型）MongoDB/PostgreSQL请使用对应产品的API




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBBinlogBackup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBBinlogBackup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Offset** | int | 分页显示的起始偏移，列表操作则指定 |**Yes**|
| **Limit** | int | 分页显示的条目数，列表操作则指定 |**Yes**|
| **DBId** | string | DB实例Id，如果指定，则只获取该db的备份信息; 当Type为2时必填 |No|
| **BeginTime** | int | 过滤条件:起始时间(时间戳) |No|
| **EndTime** | int | 过滤条件:结束时间(时间戳) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*BinlogBackupSet*](#BinlogBackupSet)] | Binlog备份信息 参见BinlogBackupSet |No|
| **TotalCount** | int | 备份总数，如果指定dbid，则是该db备份总数 |No|

#### 数据模型


#### BinlogBackupSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BackupId** | int | 备份id |No|
| **BackupName** | string | 备份名称 |No|
| **BackupTime** | int | 备份时间 |No|
| **BackupSize** | int | 备份文件大小 |No|
| **State** | string | 备份状态 Backuping // 备份中 Success // 备份成功 Failed // 备份失败 Expired // 备份过期 |No|
| **BinlogType** | string | binlog备份类型 Manual:手动备份 ,Auto:自动备份 |No|
| **DBId** | string | dbid |No|
| **ServerId** | string | 节点标识ID  |No|
| **LogStartTime** | int | 日志开始时间 |No|
| **LogEndTime** | int | 日志结束时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBBinlogBackup
&Region=gNAvFCyO
&Zone=KDHzwwya
&ProjectId=WkNtMEyG
&Offset=8
&Limit=7
&Type=12
&Types.N=4
&DBId=RFMjcVCt
&BeginTime=4
&EndTime=7
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBBinlogBackupResponse",
  "DataSet": [
    {
      "BackupId": 3,
      "BackupName": "DwxKzVqP",
      "BackupSize": 3,
      "BackupTime": 5,
      "BackupType": 4,
      "BackupZone": "WpMTrrKC",
      "BinlogType": "OlcVXUHe",
      "DBId": "ARAqnTdp",
      "DBName": "fWTAzrvH",
      "State": "BjNSkrQf",
      "Zone": "mComZFLQ"
    }
  ],
  "RetCode": 0,
  "TotalCount": 8
}
```





