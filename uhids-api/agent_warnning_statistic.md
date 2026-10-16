# 服务器状态统计 - AgentWarnningStatistic

## 简介

统计总主机数，在线数，离线数，有风险主机数，无风险主机数









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AgentWarnningStatistic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | [*AgentWarnningStatisticInfo*](#AgentWarnningStatisticInfo) | 主机状态统计结果值 |**Yes**|

#### 数据模型


#### AgentWarnningStatisticInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AgentTotal** | int | 主机总数 |**Yes**|
| **Online** | int | 在线主机数 |**Yes**|
| **Offline** | int | 离线主机数 |**Yes**|
| **WarnningCount** | int | 有风险主机数 |**Yes**|
| **SafeCount** | int | 无风险主机数 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AgentWarnningStatistic
&ProjectId=ncSDLcIT
```

### 响应示例
    
```json
{
  "Action": "AgentWarnningStatisticResponse",
  "Result": {},
  "RetCode": 0
}
```





