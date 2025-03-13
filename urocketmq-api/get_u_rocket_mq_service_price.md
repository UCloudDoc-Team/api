# 获取 URocketMQ 价格 - GetURocketMQServicePrice

## 简介

获取 URocketMQ 价格









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetURocketMQServicePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Storage** | int | 存储空间大小,单位：G，仅支持100的倍数 |**Yes**|
| **TPS** | int | 规格，每秒生产消费的数据条数。 |**Yes**|
| **ChargeType** | string | 计费模式，枚举：Dynamic：按时付费，Month：按月付费，Year：按年付费 |**Yes**|
| **Mode** | string | 实例网络类型，唯一值:PrivateNet |**Yes**|
| **Edition** | string | 版本类别，唯一值:Enterprise |**Yes**|
| **Quantity** | int | 购买时长。默认: 1。按小时购买(Dynamic)时无需此参数。 月付时，此参数传 0，代表了购买至月末。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*PriceSet*](#PriceSet)] | 价格信息 |No|

#### 数据模型


#### PriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeName** | string | 支付名称 |**Yes**|
| **ChargeType** | string | 计费类型。Year，Month，Dynamic |No|
| **Price** | float | 价格，单位: 元，保留小数点后两位有效数字 |No|
| **OriginalPrice** | float | 限时优惠的折前原价（即列表价乘以商务折扣后的单价）。 |No|
| **ListPrice** | float | 产品列表价。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetURocketMQServicePrice
&Region=cn-zj
&ProjectId=EDrREhlt
&Count=2
&TopicCount=3
&Storeage=4
&TPS=8
&ChargeType=Year
&Quantity=5
&Mode=MFHZPoBl
&Edition=TJGYKNBp
```

### 响应示例
    
```json
{
  "Action": "GetURocketMQServicePriceResponse",
  "Message": "jLNxdrBn",
  "PriceSet": [
    {
      "ChargeType": "Year",
      "ListPrice": 2.66692,
      "OriginalPrice": 5.59429,
      "Price": 7.32358
    }
  ],
  "RetCode": 0
}
```





