# 切换agent的功能版本 - SwitchAgentFunctionVersion

## 简介

对agent在各个功能版本之间切换









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SwitchAgentFunctionVersion`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|
| **FuncVersion** | int | 功能版本(0-基础版 1-企业版) |**Yes**|
| **AgentList** | string | 操作的Agent列表，以逗号分隔，如全部则设成ALL |**Yes**|
| **ChargeType** | int | 付费类型 月付或年付 |**Yes**|
| **Quantity** | int | 购买数量 |No|
| **Coupon** | string | 代金券 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Records** | [*SwitchAgentRecord*](#SwitchAgentRecord) | 切换 Agent 版本结果 |No|

#### 数据模型


#### SwitchAgentRecord

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AgentID** | string |  |No|
| **RetCode** | int |  |No|
| **Message** | string |  |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SwitchAgentFunctionVersion
&ProjectId=WJRalMZM
&FuncVersion=7
&AgentList=FivBWYyj
&ChargeType=3
&Quantity=6
&Coupon=KMzrxygC
```

### 响应示例
    
```json
{
  "Action": "SwitchAgentFunctionVersionResponse",
  "Records": {},
  "RetCode": 0
}
```





