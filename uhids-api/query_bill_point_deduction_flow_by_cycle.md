# 按照周期统计用户计费点数变化情况 - QueryBillPointDeductionFlowByCycle

## 简介

按照周期(目前只支持按天)统计用户计费点数变化(增加/减少/预留)情况









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryBillPointDeductionFlowByCycle`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|
| **Type** | string | 周期(可用值:day) |**Yes**|
| **StartTime** | string | (可选)查询开始时间，格式xxxx-xx-xx |No|
| **EndTime** | string | (可选)查询结束时间，格式xxxx-xx-xx |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | array[[*CycleBillPointStat*](#CycleBillPointStat)] | 返回的数据 |No|

#### 数据模型


#### CycleBillPointStat

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | string | 统计时间 |**Yes**|
| **SubPointNum** | int | 增加的点数 |**Yes**|
| **AddPointNum** | int | 减少的减少 |**Yes**|
| **RemainPointNum** | int | 余留的点数 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryBillPointDeductionFlowByCycle
&ProjectId=ViRJHBkS
&Type=BmCRsszk
&StartTime=zSLhhENJ
&EndTime=HnSmEist
```

### 响应示例
    
```json
{
  "Action": "QueryBillPointDeductionFlowByCycleResponse",
  "Result": [
    {
      "AddPointNum": 4,
      "RemainPointNum": 3,
      "SubPointNum": 5,
      "Time": "TcRxrYJJ"
    }
  ],
  "RetCode": 0
}
```





