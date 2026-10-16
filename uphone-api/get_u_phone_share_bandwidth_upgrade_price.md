# 获取云手机共享带宽升降级价格 - GetUPhoneShareBandwidthUpgradePrice

## 简介

获取云手机共享带宽升降级价格









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUPhoneShareBandwidthUpgradePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ShareBandwidthId** | string | 共享带宽的ID |**Yes**|
| **Bandwidth** | int | 需要升降级的带宽，默认是当前带宽大小 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | float | 规格调整差价。单位: 元，保留小数点后两位有效数字 |**Yes**|
| **OriginalPrice** | float | 限时优惠的折前原价（即列表价乘以商务折扣后的单价） |**Yes**|
| **ListPrice** | float | 产品列表价 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUPhoneShareBandwidthUpgradePrice
&ProjectId=LEkeqLDl
&CityId=biQEMOKs
&ShareBandwidthId=CEuXEWMG
&Bandwidth=4
```

### 响应示例
    
```json
{
  "Action": "GetUPhoneShareBandwidthUpgradePriceResponse",
  "ListPrice": 1.89395,
  "Message": "jKtPhhej",
  "OriginalPrice": 4.88479,
  "Price": 6.96383,
  "RetCode": 0
}
```





