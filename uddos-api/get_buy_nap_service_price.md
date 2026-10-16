# 获取高防价格 - GetBuyNapServicePrice

## 简介

获取高防价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetBuyNapServicePrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetBuyNapServicePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AreaLine** | string | 地区线路 |**Yes**|
| **EngineRoom.N** | string | 地区 |**Yes**|
| **LineType** | string | 线路类型 |**Yes**|
| **ChargeType** | string | 计费方式 |**Yes**|
| **Quantity** | string | 计费时长 |**Yes**|
| **DefenceDDosBaseFlowArr.N** | string | DDoS基础防护流量 |**Yes**|
| **DefenceDDosMaxFlowArr.N** | string | DDoS最大防护流量 |**Yes**|
| **SrcBandwidth** | string | 带宽 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 价格 |**Yes**|
| **FreeIPQuota** | int | 免费IP配额 |**Yes**|
| **ChargeIPQuota** | int | 收费IP配额 |**Yes**|
| **UdpFreeIpQuota** | int | UDP免费IP配额 |**Yes**|
| **OriginalPrice** | float | 原价 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetBuyNapServicePrice
&TopOrganizationId=UowUWFkg
&OrganizationId=9
&Quantity=zCtSLCOM
&SrcBandwidth=ojuxgbHz
&ChargeIPQuota=qgOrcebm
&DefenceDDosBaseFlowArr.0=aJVnXrvn
&DefenceDDosMaxFlowArr.0=eAciEPQO
&AccessMode=UOGAOzZm
&ChargeType=oVOTeZKk
&ChargeType=AhwfaDci
&LineType=dugKEtmb
&EngineRoom.0=KvmpgjuU
&AreaLine=GgFGenxN
&ChargeType=ZrsiVFsn
&LineType=UyPUzyjP
&EngineRoom.N=zsdDSKgQ
&AreaLine=gtodGakr
&AreaLine=eERArywj
&EngineRoom.N=MRyVvmaX
&LineType=SAekKMEt
&ChargeType=BhRHtDGR
&ChargeIPQuota=AvdLsjbt
```

### 响应示例
    
```json
{
  "Action": "GetBuyNapServicePriceResponse",
  "ChargeIPQuota": "abtFToFm",
  "FreeIPQuota": "jLXnmyuD",
  "Message": "OakHySwp",
  "OriginalPrice": 8.57352,
  "Price": 4.51533,
  "RetCode": 0,
  "UdpFreeIpQuota": "EUCgQsWk"
}
```





