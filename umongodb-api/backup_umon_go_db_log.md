# 集群日志打包  - BackupUMongoDBLog

## 简介

日志打包






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=BackupUMongoDBLog)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BackupUMongoDBLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Name** | string | 日志包名称 |**Yes**|
| **ClusterId** | string | 集群id |**Yes**|
| **NodeId** | string | 节点id, 慢日志 mongos 节点不可选 |**Yes**|
| **Begin** | int | 日志开始时间,最早为7x24小时前 |**Yes**|
| **End** | int | 日志结束时间,时间区间不能超过24小时 |**Yes**|
| **LogType** | string | 日志类型:SlowLog,ErrorLog |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BackupUMongoDBLog
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=ndyCAElz
&Name=bMrgJltF
&ClusterId=RhaQNXRs
&NodeId=xVfbZIuK
&Begin=6
&End=2
&LogType=Slow_Log
```

### 响应示例
    
```json
{
  "Action": "BackupUMongoDBLogResponse",
  "RetCode": 0
}
```





