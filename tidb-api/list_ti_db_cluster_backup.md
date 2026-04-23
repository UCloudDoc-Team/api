# 列出按实例备份tidb的备份列表 - ListTiDBClusterBackup

## 简介

列出按实例备份tidb的备份列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListTiDBClusterBackup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListTiDBClusterBackup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Id** | string | 实例id |**Yes**|
| **Limit** | int | 返回数据长度，默认为30，最大30 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*BackupData*](#BackupData) | 备份信息 |**Yes**|
| **TotalCount** | int | 备份总数 |No|

#### 数据模型


#### BackupData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BackupId** | string | 备份 ID |**Yes**|
| **BackupStartTime** | int | 备份起始时间 |**Yes**|
| **BackupEndTime** | int | 备份结束时间 |**Yes**|
| **BackupSize** | int | 备份文件大小，单位：MB |**Yes**|
| **State** | string | 备份状态 |**Yes**|
| **BackupType** | string | 备份方式 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListTiDBClusterBackup
&Region=cn-zj
&Id=MlaMfzgZ
&Limit=7
&Offset=7
```

### 响应示例
    
```json
{
  "Action": "ListTiDBClusterBackupResponse",
  "BackupData": {},
  "RetCode": 0,
  "TotalCount": 8
}
```





