# 获取云游戏服务器带宽价格 - GetUGameIPPrice

## 简介

获取云游戏服务器带宽价格









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUGameIPPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CityId** | string | 城市ID |**Yes**|
| **Bandwidth** | string | 带宽，100 - 600 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为： > Year，按年付费； > Month，按月付费； 如果不传某个枚举值，默认返回年付、月付的价格组合集。 |No|
| **Quantity** | string | 购买时长。默认: 1。 月付时，此参数传0，代表了购买至月末。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*ServerPriceSet*](#ServerPriceSet)] | 价格列表，每项参数见ServerPriceSet |**Yes**|

#### 数据模型


#### ServerPriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费类型，枚举值：Year，Month |**Yes**|
| **Price** | float | 价格，单位: 元，保留小数点后两位有效数字 |**Yes**|
| **OriginalPrice** | float | 限时优惠的折前原价（即列表价乘以商务折扣后的单价） |**Yes**|
| **ListPrice** | float | 产品列表价 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUGameIPPrice
&ProjectId=ijMMTYSW
&CityId=qaXpDRun
&ChargeType=TRVhWRTl
&Bandwidth=wgQosjxH
&Quantity=rYOOIdUC
```

### 响应示例
    
```json
{
  "Action": "GetUGameIPPriceResponse",
  "Message": "UdsFIGrB",
  "PriceSet": [
    {
      "ChargeType": "dsTYLoKF",
      "ListPrice": 7.78415,
      "OriginalPrice": 6.61474,
      "Price": 4.48295
    }
  ],
  "RetCode": 0
}
```





