# WAF攻击源IP数概览 - StatWafAttackSrcTrend

## 简介

WAF攻击源IP数概览









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `StatWafAttackSrcTrend`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID，不填表示默认项目 |No|
| **BeginTime** | int | 起始时间，时间戳，单位：秒 |**Yes**|
| **EndTime** | int | 终止时间，时间戳，单位：秒 |**Yes**|
| **Domain** | string | 要统计的域名 |No|
| **Extent** | int | 统计区间，单位：秒，取值范围0-7200 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | [*StatAttackSrcResult*](#StatAttackSrcResult) | 攻击详情，参考StatAttackSrcResult |No|

#### 数据模型


#### StatAttackSrcResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Count** | int | 返回节点个数 |**Yes**|
| **Detail** | array[[*StatAttackSrcDetail*](#StatAttackSrcDetail)] | 攻击源详情数组，参考StatAttackSrcDetail |**Yes**|

#### StatAttackSrcDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Timestamp** | int | 时间戳 |**Yes**|
| **Count** | int | 攻击次数 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=StatWafAttackSrcTrend
&ProjectId=org-xxx
&BeginTime=1586237414
&EndTime=1586241014
```

### 响应示例
    
```json
{
  "Action": "StatWafAttackSrcTrendResponse",
  "Result": {
    "Count": 3,
    "Detail": [
      {
        "Count": 1,
        "Timestamp": 1586240820
      },
      {
        "Count": 1,
        "Timestamp": 1586240880
      },
      {
        "Count": 1,
        "Timestamp": 1586240940
      }
    ],
    "Type": "AttackSrcIP"
  },
  "RetCode": 0
}
```





