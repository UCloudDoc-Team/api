# 列出实例恢复列表 - ListTiDBClusterRestore

## 简介

列出实例恢复列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListTiDBClusterRestore)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListTiDBClusterRestore`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Id** | string | 实例的服务Id |**Yes**|
| **Limit** | int | 返回数据长度，默认为30，最大30 |**Yes**|
| **Offset** | int | 列表起始位置偏移量，默认为0 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RestoreData** | [*RestoreData*](#RestoreData) | 恢复信息 |**Yes**|

#### 数据模型


#### RestoreData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RestoreId** | string | 恢复的Id |**Yes**|
| **SourceServiceId** | string | 源实例Id |**Yes**|
| **TargetServiceId** | string | 目标实例Id |**Yes**|
| **BackupId** | string | 备份Id |**Yes**|
| **RestoreStartTime** | int | 恢复的起始时间 |**Yes**|
| **RestoreEndTime** | int | 恢复的结束时间 |**Yes**|
| **State** | string | 恢复的状态 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListTiDBClusterRestore
&Region=cn-zj
&Id=HCHVCrcr
&Limit=8
&Offset=3
```

### 响应示例
    
```json
{
  "Action": "ListTiDBClusterRestoreResponse",
  "RestoreData": {},
  "RetCode": 0
}
```





