# 获取简洁版带宽包价格 - GetSimpleBuyBwPrice

## 简介

获取简洁版带宽包价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetSimpleBuyBwPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetSimpleBuyBwPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **RegionA** | string | 地域 A 名称 |**Yes**|
| **RegionB** | string | 地域 B 名称 |**Yes**|
| **PayMode** | string | 计费模式 FixedBw:固定带宽｜Max5:第五峰值｜Traffic:流量计费 <br />固定带宽：按月/按年 <br />Max5：后付费 <br />流量计费：按量付费 |**Yes**|
| **ChargeType** | string | 付费方式 Month:按月｜Year:按年｜PostPay:后付费｜Count:按量 |**Yes**|
| **Qos** | string | 服务质量 Diamond:钻石｜Platinum:铂金｜Gold:黄金 |**Yes**|
| **Path** | string | 智能路径 Delay:最低时延｜IGP:普通线路｜TCO:最低成本 |**Yes**|
| **BandWidth** | int | 购买的带宽值，默认为1 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalPrice** | int | 最终价格 = 原价 * 用户折扣 * 产品折扣 |**Yes**|
| **CustomPrice** | int | 客户折扣价 = 原价 * 用户折扣 |**Yes**|
| **OriginalPrice** | int | 原价 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetSimpleBuyBwPrice
&RegionA=fRpJDnxZ
&RegionB=eKMkSCGn
&PayMode=JAJikQtx
&ChargeType=uiBMSaYK
&Qos=XNOubKqj
&Path=PyruDAeA
&BandWidth=6
&ProjectId=dYgxmVoW
```

### 响应示例
    
```json
{
  "Action": "GetSimpleBuyBwPriceResponse",
  "CustomPrice": 9,
  "OriginalPrice": 2,
  "RetCode": 0,
  "TotalPrice": 8
}
```





