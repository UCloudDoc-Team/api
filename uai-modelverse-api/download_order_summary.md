# 下载订单汇总 - DownloadOrderSummary

## 简介

生成订单汇总 Excel 文件（包含已完成订单和欠费订单两个 sheet），返回 US3 预签名下载链接；StartTime/EndTime 必填






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DownloadOrderSummary)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DownloadOrderSummary`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **StartTime** | int | 查询开始时间（Unix 时间戳，秒级），必填 |**Yes**|
| **EndTime** | int | 查询结束时间（Unix 时间戳，秒级），必填；必须大于 StartTime |**Yes**|
| **ResourceIds.N** | string | 资源ID列表（可选） |No|
| **ModelIds.N** | string | 模型ID列表（可选） |No|
| **PricingUnits.N** | int | 计费单位列表（多选，可选） |No|
| **OrderTypes.N** | int | 订单类型数组（多选，可选） |No|
| **ChargeTypes.N** | int | 计费类型数组（多选，可选） |No|
| **OrganizationIds.N** | int | 组织ID列表（可选） |No|
| **Regions.N** | string | 地域列表（可选），参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **PricingSkus.N** | string | 计费单元（SKU）列表（可选） |No|
| **ProductCodes.N** | string | 产品类型列表（可选），枚举值：`modelverse`、`sandbox` |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*DownloadFileData*](#DownloadFileData) | 下载文件信息 |**Yes**|

#### 数据模型


#### DownloadFileData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DownloadURL** | string | 文件下载链接（US3 预签名 URL，请在有效期内立即下载） |No|
| **FileName** | string | 文件名 |No|
| **FileSize** | int | 文件大小（字节） |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DownloadOrderSummary
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=ZVFLqbxn
&ResourceIds.N=BONixqED
&ModelIds.N=nCcsbuQl
&PricingUnits.N=7
&OrderTypes.N=5
&ChargeTypes.N=4
&StartTime=8
&EndTime=4
&ResourceIds.N=xYoOQLWh
&ModelIds.N=rWnTQfwE
&PricingUnits.N=3
&OrderTypes.N=4
&ChargeTypes.N=4
&StartTime=3
&EndTime=6
&OrganizationIds.N=2
&Regions.N=DocWWrys
&PricingSkus.N=rYuUvYgY
&ProductCodes.N=nzsleIUe
```

### 响应示例
    
```json
{
  "Action": "DownloadOrderSummaryResponse",
  "Data": {},
  "RetCode": 0
}
```





