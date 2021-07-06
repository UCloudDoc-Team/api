# 获取流量计费EIP每日流量计费信息 - GetThroughputDailyBillingInfo

## 简介

获取流量计费EIP每日流量计费信息

?> EIP采用带宽计费时，按0记录当日流量。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetThroughputDailyBillingInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetThroughputDailyBillingInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **EIPId** | string | EIP的资源ID |**Yes**|
| **StartTime** | int | 查询开始时间时间戳 |**Yes**|
| **EndTime** | int | 查询结束时间时间戳 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Stats** | array[[*ThroughputDailyBillingInfo*](#ThroughputDailyBillingInfo)] | EIP流量计费信息，详见模型ThroughputDailyBillingInfo |No|
| **TotalOutMoney** | int | 计费总金额 |No|
| **TotalOutSize** | string | 计费总流量 |No|

#### 数据模型


#### ThroughputDailyBillingInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **StartTime** | int | 计费开始时间 |No|
| **EndTime** | int | 计费结束时间 |No|
| **QuantityOutSize** | int | 计费流量，单位“GB” |No|
| **QuantityOutMoney** | int | 计费金额，单位“元” |No|
| **BillingState** | string | 是否已计费，“Yes”或者“No” |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetThroughputDailyBillingInfo
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=AsxKOJdn
&EIPId=OcgPtYAG
&StartTime=6
&EndTime=5
```

### 响应示例
    
```json
{
  "Action": "GetThroughputDailyBillingInfoResponse",
  "RetCode": 0,
  "Stats": [
    {
      "BillingState": "syykRjZm",
      "EndTime": 3,
      "QuantityOut": 8,
      "StartTime": 4
    }
  ],
  "TotalOut": 3,
  "TotalOutSize": "QCZguxjs"
}
```





