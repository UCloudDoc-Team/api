# (新)获取UDB的日志备份地址 - DescribeUDBBinlogBackupURL

## 简介

获取UDB的Binlog或者错误日志或者慢查询日志的备份地址



!> 不支持新版（NVMe型）MongoDB/PostgreSQL， 新版（NVMe型）MongoDB/PostgreSQL请使用对应产品的API


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUDBBinlogBackupURL)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUDBBinlogBackupURL`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **DBId** | string | DB实例Id |**Yes**|
| **BackupId** | int | DB实例日志备份ID，可以从DescribeUDBLogPackage结果当中获得 |**Yes**|
| **BinlogType** | string | binlog备份类型 Manual:手动备份 ,Auto:自动备份 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BackupPath** | string | DB实例备份文件的公网地址 |No|
| **InnerBackupPath** | string | DB实例备份文件的内网地址 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUDBBinlogBackupURL
&Region=cn-bj2
&DBId=udb-xxxxxx
&BackupId=1234
&BinlogType=vqVtwBwj
```

### 响应示例
    
```json
{
  "Action": "DescribeUDBBinlogBackupURLResponse",
  "BackupPath": "http://udbbackup.ufile.ucloud.cn/bbasd?UCloudPublicKey=ucloududb@ucloud.cn1426152414000604875621\u0026Expires=1426761552\u0026Signature=8MEqKJlwRVLWI1ZvLE/23pveM=",
  "InnerBackupPath": "yurdmcLI",
  "RetCode": 0
}
```





