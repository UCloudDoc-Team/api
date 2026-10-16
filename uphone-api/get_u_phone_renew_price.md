# 获取云手机续费价格 - GetUPhoneRenewPrice

## 简介

获取云手机续费价格，不包括独立ip价格。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUPhoneRenewPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UPhoneId** | string | 云手机的唯一标识，可通过[查询云手机列表]获取。 |**Yes**|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |No|
| **ChargeType** | string | 计费模式。枚举值为： > Year，按年付费； > Month，按月付费； > Dynamic，按小时预付费; 默认返回全部计费方式对应的价格 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*UPhonePriceSet*](#UPhonePriceSet)] | 价格列表,具体参数见UPhonePriceSet |**Yes**|

#### 数据模型


#### UPhonePriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费类型，枚举值：Year，Month，Dynamic |**Yes**|
| **Price** | float | 价格，单位: 元，保留小数点后两位有效数字<br /> |**Yes**|
| **OriginalPrice** | float | 限时优惠的折前原价（即列表价乘以商务折扣后的单价）<br /> |**Yes**|
| **ListPrice** | float | 产品列表价<br /> |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUPhoneRenewPrice
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=ukVpkCgO
&UPhoneId=CSdydgqB
&CityId=BTlqcIgU
&ChargeType=SbXguVpa
```

### 响应示例
    
```json
{
  "Action": "GetUPhoneRenewPriceResponse",
  "PriceSet": [
    {
      "ChargeType": "Ujiwzbss",
      "ListPrice": 4.29728,
      "OriginalPrice": 7.84374,
      "Price": 7.43913
    }
  ],
  "RetCode": 0
}
```





