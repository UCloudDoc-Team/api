# 获取全球统一接入转发实例价格 - GetUGA3Price

## 简介

获取全球统一接入转发实例价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUGA3Price)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUGA3Price`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Bandwidth** | int | 共享带宽大小 |**Yes**|
| **AreaCode** | string | 源站区域 |**Yes**|
| **Quantity** | int | 购买时间数量，当ChargeType为Month时 Quantity默认为0，代表购买至月底。按年按小时必须为大于0 |No|
| **ChargeType** | string | 计费方式，默认按月支付。Month: 按月; Year: 按年; Dynamic: 按小时收 |No|
| **AccelerationArea** | string | 加速大区,默认返回所有加速大区价格 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGA3Price** | array[[*UGA3Price*](#UGA3Price)] | 加速大区对应价格 |**Yes**|

#### 数据模型


#### UGA3Price

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AccelerationArea** | string | 加速大区代码 |**Yes**|
| **AccelerationAreaName** | string | 加速大区名称 |**Yes**|
| **AccelerationForwarderPrice** | float | 转发配置价格 |**Yes**|
| **AccelerationBandwidthPrice** | float | 加速配置带宽价格 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUGA3Price
&ProjectId=OrwijfHZ
&Bandwidth=2
&Quantity=3
&ChargeType=Year
&AccelerationArea=AoixLFuJ
&AreaCode=DFFsIckA
```

### 响应示例
    
```json
{
  "Action": "GetUGA3PriceResponse",
  "Price": 5.63311,
  "RetCode": 0
}
```





