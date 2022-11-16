# 实例备份列表 - ListUMongoDBBackup

## 简介

拉取实例备份列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUMongoDBBackup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUMongoDBBackup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ClusterId** | string | 实例ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*BackupInfo*](#BackupInfo)] | 备份列表 |**Yes**|

#### 数据模型


#### BackupInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BackupId** | string | 备份ID |**Yes**|
| **BackupName** | string | 备份名称 |No|
| **ClusterId** | string | 实例ID |No|
| **State** | string | 备份状态 |No|
| **BackupSize** | int | 备份数据大小 |No|
| **BackupType** | string | 备份类型 |No|
| **StartTime** | int | 备份开始时间 |No|
| **EndTime** | int | 备份结束时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUMongoDBBackup
&Region=cn-zj
&Zone=cn-zj-01
&ClusterId=yyKqkWlP
```

### 响应示例
    
```json
{
  "Action": "ListUMongoDBBackupResponse",
  "DataSet": [
    {
      "BackupId": "nbhssxzI",
      "BackupName": "LRvVcdWF",
      "BackupSize": 9,
      "BackupType": "EKheYLoc",
      "ClusterId": "BDpDJqTk",
      "EndTime": 7,
      "StartTime": 4,
      "State": "fjLdqjUb"
    }
  ],
  "Message": "ogIzkoBe",
  "RetCode": 0
}
```





