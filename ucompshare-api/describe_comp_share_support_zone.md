# 获取支持的可用区信息列表 - DescribeCompShareSupportZone

## 简介

获取支持的可用区信息列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeCompShareSupportZone`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ZoneInfo** | array[[*SupportZone*](#SupportZone)] | 可用区信息列表 |**Yes**|

#### 数据模型


#### SupportZone

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域名称 |No|
| **Zone** | string | 可用区名称 |No|
| **RegionId** | int | 地域ID |No|
| **ZoneId** | int | 可用区ID |No|
| **Describe** | string | 可用区显示名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeCompShareSupportZone
&Region=cn-zj
```

### 响应示例
    
```json
{
  "Action": "DescribeCompShareSupportZoneResponse",
  "RetCode": 0,
  "ZoneInfo": [
    {
      "Region": "TXsViMYV",
      "RegionId": 1,
      "Zone": "NrbBefbh",
      "ZoneId": 2
    }
  ]
}
```





