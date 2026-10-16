# 获取高防升降级价格 - DescribeUpgradeHighProtectGameServicePrice

## 简介

获取高防升降级价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUpgradeHighProtectGameServicePrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUpgradeHighProtectGameServicePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |**Yes**|
| **DefenceType** | string | 防御类型，默认为TypeFixed |No|
| **LineType** | string | 线路 |No|
| **DefenceDDosMaxFlowArr.N** | string | DDoS基础防护值 |No|
| **DefenceDDosBaseFlowArr.N** | string | DDoS弹性防护值 |No|
| **EngineRoom.N** | string | 代表机房，例如Dongguan  Hangzhou |No|
| **AreaLine** | string | 区域，华东和华南，EastChina 和SouthChina |No|
| **SrcBandwidth** | int | 带宽，默认100M |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 价格 |**Yes**|
| **OriginalPrice** | float | 原价 |No|
| **FreeIPQuota** | int | 免费IP配额 |No|
| **ChargeIPQuota** | int | 收费IP配额 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUpgradeHighProtectGameServicePrice
&DefenceType="TypeFixed"
&DefenceDDosBaseFlow=10
&DefenceDDosMaxFlow=20
&LineType="BGP"
&ResourceId="31db0df1-08c5-4547-8ccc-c2d99108403c"
&DefenceDDosMaxFlowArr="20,20"
&DefenceDDosBaseFlowArr="10,10"
&EngineRoom="Hangzhou"
&AreaLine="EastChina"
&SrcBandwidth=100
&ChargeIPQuota=2
```

### 响应示例
    
```json
{
  "Action": "DescribeUpgradeHighProtectGameServicePriceResponse",
  "ChargeIPQuota": 3,
  "FreeIPQuota": 3,
  "OriginalPrice": 4.21538,
  "Price": 123,
  "RetCode": 0
}
```





