# 续费高防服务 - RenewHighProtectGameService

## 简介

续费高防服务






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=RenewHighProtectGameService)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `RenewHighProtectGameService`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |**Yes**|
| **ChargeType** | string | 计费方式 |**Yes**|
| **Quantity** | int | 购买数量 |**Yes**|
| **LineType** | string | 线路 |**Yes**|
| **AreaLine** | string | 区域，华东和华南，EastChina 和SouthChina |**Yes**|
| **SrcBandwidth** | int | 带宽，默认100M |**Yes**|
| **EngineRoom.N** | string | 代表机房，例如Dongguan  Hangzhou |**Yes**|
| **DefenceType** | string | 防御类型，默认为TypeFixed |No|
| **DefenceDDosMaxFlowArr.N** | string | DDoS弹性防御值 |No|
| **DefenceDDosBaseFlowArr.N** | string | DDoS基础防御值 |No|
| **CouponId** | string | 代金券ID |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ResourceInfo** | [*ResourceInfo*](#ResourceInfo) | 资源信息 |**Yes**|

#### 数据模型


#### ResourceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源id |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=RenewHighProtectGameService
&ChargeType="Month"
&DefenceType="TypeFixed"
&DefenceDDosBaseFlow=10
&DefenceDDosMaxFlow=20
&Quantity=1
&CouponId="kdljdoskd"
&HighProtectGameServiceName="test"
&LineType="BGP"
&ResourceId="20b56aca-81b1-497d-86e8-aa7d02d67289"
&ChangePayMode="BuyGame"
&DefenceDDosMaxFlowArr="10,10"
&DefenceDDosBaseFlowArr="10,10"
&EngineRoom="Hangzhou"
&AreaLine="EastChina"
&SrcBandwidth=100
&ChargeIPQuota=2
```

### 响应示例
    
```json
{
  "Action": "RenewHighProtectGameServiceResponse",
  "ResourceInfo": "[]",
  "RetCode": 0
}
```





