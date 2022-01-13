# 获取UInfluxdb价格 - DescribeUInfluxdbPrice

## 简介

获取UInfluxdb价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUInfluxdbPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUInfluxdbPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CpuLimit** | int | 核数 单位：个，规格［2C8G, 4C16G, 8C32G, 16C64G, 32C128G］ |**Yes**|
| **ChargeType** | string | 付费类型，后付费。填：PostPaid (后付费) |No|
| **MemoryLimit** | int | 内存限制 单位：G 规格 [2C8G, 4C16G, 8C32G, 16C64G, 32C128G］ |No|
| **Quantity** | int | 付费周期数量 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 价格 |**Yes**|
| **OriginalPrice** | float | 原价 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUInfluxdbPrice
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=zOYuUYld
&QPS=8
&Capacity=9
&CpuLimit=9
&Quantity=uRVPMPqa
&ChargeType=WDlEzmgl
&ChargeType=WBbXKpvF
&ChargeType=hNdRTATt
&ChargeType=OWyKFAiW
&MemoryLimit=eZtOFOWI
&MemoryLimit=3
&Quantity=4
&Quantity=3
```

### 响应示例
    
```json
{
  "Action": "DescribeUInfluxdbPriceResponse",
  "OriginalPrice": 6.32923,
  "Price": 9.61517,
  "RetCode": 0
}
```





