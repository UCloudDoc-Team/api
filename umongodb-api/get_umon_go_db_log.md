# 获取集群节点日志 - GetUMongoDBLog

## 简介

查询某一段时间内集群节点的错误日志或慢查询日志






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUMongoDBLog)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUMongoDBLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterId** | string | 集群id |**Yes**|
| **NodeId** | string | 节点id, 慢日志 mongos 节点不可选 |**Yes**|
| **Begin** | int | 查询的日志开始的时间戳（Unix Timestamp）。对于实时查询，这个参数应该是上次轮询请求时的时间戳，后台会返回从该值到当前时间的日志内容 |**Yes**|
| **LogType** | string | 日志类型:SlowLog,ErrorLog |**Yes**|
| **End** | int | 查询日志的结束时间戳(Unix Timestamp），对于实时查询不传该值，与BeginTime的差值不超过24小时：(EndTime-BeginTime) < 24*60*60 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Log** | string | 查询到的日志内容，一段纯文本 |**Yes**|
| **MaxLine** | int | 支持的最大行数 |No|
| **IsTruncate** | boolean | 是否已被截断 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUMongoDBLog
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=RNIPzEei
&NodeId=lWaoAKsr
&Begin=4
&LogType=cSfGujbe
&End=6
&ClusterId=ZTYDWNOp
```

### 响应示例
    
```json
{
  "Action": "GetUMongoDBLogResponse",
  "IsTruncate": true,
  "Log": "nZKlllSk",
  "MaxLine": 1,
  "NextTime": "auUFaISM",
  "RetCode": 0
}
```





