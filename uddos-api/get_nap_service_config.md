# 获取高防服务配置 - GetNapServiceConfig

## 简介

获取高防服务配置






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNapServiceConfig)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNapServiceConfig`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AreaLine** | string | 线路区域 |No|
| **EngineRoom** | string | 购买的套餐所在机房 |No|
| **LineType** | string | 线路类型 |No|
| **NapType** | int | 高防类型；0：全部、1：内地高防、:2：海外高防 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NapServiceConfig** | array[[*NapServiceConfigEntry*](#NapServiceConfigEntry)] | 高防服务配置 |**Yes**|

#### 数据模型


#### NapServiceConfigEntry

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AreaLine** | string | 线路区域 |No|
| **EngineRoom** | string | 购买的套餐所在机房 |No|
| **LineType** | string | 线路类型 |No|
| **DR** | object | 灾备配置 |No|
| **Domain** | object | 域名配置 |No|
| **DomainSrc** | object | 是否可以配置域名回源 |No|
| **DynamicPay** | object | 按需购买配置 |No|
| **DayPay** | object | 按天购买配置 |No|
| **MonthPay** | object | 按月购买配置 |No|
| **YearPay** | object | 按年购买配置 |No|
| **NapType** | int | 高防类型，1：内地高防、2：海外高防 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNapServiceConfig
&AreaLine=EastChina
&EngineRoom=Huzhou
&LineType=DUPLET
&NapType=UQnUagoI
```

### 响应示例
    
```json
{
  "Action": "GetNapServiceConfigResponse",
  "NapServiceConfig": [
    {
      "AreaLine": "EastChina",
      "DR": null,
      "DayPay": null,
      "Domain": {
        "Enable": true
      },
      "DomainForward": {
        "Enable": false
      },
      "DomainSrc": {
        "Enable": true
      },
      "DynamicPay": null,
      "EngineRoom": "Huzhou",
      "LineType": "DUPLET",
      "MonthPay": null,
      "YearPay": null
    }
  ],
  "RetCode": 0
}
```





