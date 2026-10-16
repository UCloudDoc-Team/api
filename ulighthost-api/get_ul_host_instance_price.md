# 获取轻量应用云主机套餐价格 - GetULHostInstancePrice

## 简介

获取轻量应用云主机套餐价格 






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULHostInstancePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BundleId** | string | 套餐ID |**Yes**|
| **ChargeType** | string | 获取指定计费模式的价格。枚举值：<br /><br /> > Year，按年付费； <br /><br /> > Month。未指定时，返回所有计费模式价格 |No|
| **Count** | int | 购买台数，范围[1,5]。默认：1 |No|
| **Quantity** | int | 购买时长。默认: 1。不支持购买到月末 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*ULHostPriceSet*](#ULHostPriceSet)] | 价格 |**Yes**|

#### 数据模型


#### ULHostPriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费模式 |No|
| **Price** | float | 价格 |No|
| **OriginalPrice** | float | 原价 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULHostInstancePrice
&Region=cn-zj
&ProjectId=CGVOWzNf
&BundleId=ogJbCxRp
&ChargeType=EuTiscZq
&Count=4
&Quantity=2
```

### 响应示例
    
```json
{
  "Action": "GetULHostInstancePriceResponse",
  "Message": "vKVZkQZk",
  "PriceSet": [
    {
      "ChargeType": "KiRfqWCb",
      "ListPrice": 6.67657,
      "ListPriceDetail": {},
      "OriginalPrice": 8.63741,
      "OriginalPriceDetail": {},
      "Price": 4.88968,
      "PriceDetail": {}
    }
  ],
  "RetCode": 0
}
```





