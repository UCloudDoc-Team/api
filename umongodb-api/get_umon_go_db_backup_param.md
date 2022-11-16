# 获取实例备份策略 - GetUMongoDBBackupParam

## 简介

获取实例备份策略






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUMongoDBBackupParam)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUMongoDBBackupParam`                        | **Yes** |
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
| **DataSet** | [*BackupParam*](#BackupParam) | 备份策略信息 |**Yes**|

#### 数据模型


#### BackupParam

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ClusterId** | string | 实例ID |**Yes**|
| **AutoBackupToggleWeek** | string | 自动备份预期周几 (1-7 表示 周一到周末，多个数据用','分割，eg: 3,7) |No|
| **AutoBackupToggleTime** | string | 自动备份预期时间范围 (24小时制，精确到分钟，00:00\~23:59) |No|
| **AutoBackupCopies** | int | 自动备份保存份数 |No|
| **ManualBackupCopies** | int | 手动备份保存份数 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUMongoDBBackupParam
&Region=cn-zj
&Zone=cn-zj-01
&ClusterId=DmBGvXyK
```

### 响应示例
    
```json
{
  "Action": "GetUMongoDBBackupParamResponse",
  "DataSet": {},
  "Message": "eBkJLfZH",
  "RetCode": 0
}
```





