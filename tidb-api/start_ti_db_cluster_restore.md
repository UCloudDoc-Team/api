# 开始按实例计费tidb的恢复 - StartTiDBClusterRestore

## 简介

开始按实例计费tidb的恢复






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=StartTiDBClusterRestore)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `StartTiDBClusterRestore`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **BackupId** | string | 备份id |**Yes**|
| **Id** | string | 实例id |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RestoreId** | string | 恢复任务Id |**Yes**|
| **ServiceId** | string | 实例id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=StartTiDBClusterRestore
&Region=cn-zj
&BackupId=WjspwUvO
&Id=ltdnOqWw
```

### 响应示例
    
```json
{
  "Action": "StartTiDBClusterRestoreResponse",
  "Message": "rJfLhaPY",
  "RestoreId": "zPcTqOJC",
  "RetCode": 0,
  "ServiceId": "mPMyGJFZ"
}
```





