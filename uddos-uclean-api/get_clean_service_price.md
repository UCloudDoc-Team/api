# 获取清洗套餐的价格 - GetCleanServicePrice

## 简介

获取清洗套餐的价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetCleanServicePrice)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCleanServicePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费类型（Month:按月，Year:按年） |**Yes**|
| **CleanRegion** | string | 通过GetCleanServiceRegion 维护更新可用的地域列表以应对日益扩张的机房。截止至2019-01-24现网目前可用的列表见枚举： |**Yes**|
| **Quantity** | int | 防护时长（0代表购置月底，年底） |**Yes**|
| **MaxCleanCapacity** | int | 流量清洗上限防护流量（单位G），默认5 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | int | 清洗套餐价格 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCleanServicePrice
&ChargeType=Month
&CleanRegion=TpaukPxG
&MaxCleanCapacity=2
&Quantity=3
```

### 响应示例
    
```json
{
  "Action": "GetCleanServicePriceResponse",
  "Price": 8,
  "RetCode": 0
}
```





