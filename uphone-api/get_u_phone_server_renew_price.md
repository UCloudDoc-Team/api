# 获取云手机服务器续费价格 - GetUPhoneServerRenewPrice

## 简介

获取云手机服务器续费价格<br /><br />提示信息: 须按照控制台服务器模型配置创建服务器。详情请参考控制台。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUPhoneServerRenewPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ServerId** | string | 云手机服务器的唯一标识，可通过[查询云手机服务器列表]()获取。 |**Yes**|
| **CityId** | string | 城市Id，通过[获取城市列表](#DescribeUPhoneCities)获取 |**Yes**|
| **ChargeType** | string | 计费模式。枚举值为：<br /><br />> Year，按年付费；<br /><br />> Month，按月付费；<br /><br /> > Dynamic，按小时预付费; <br />默认返回全部计费方式对应的价格 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*UPhoneServerPriceSet*](#UPhoneServerPriceSet)] | 价格列表,具体参数见UPhoneServerPriceSet	 |**Yes**|

#### 数据模型


#### UPhoneServerPriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费类型，枚举值：Year，Month |**Yes**|
| **Price** | float | 价格，单位: 元，保留小数点后两位有效数字	 |**Yes**|
| **OriginalPrice** | float | 限时优惠的折前原价（即列表价乘以商务折扣后的单价）	 |**Yes**|
| **ListPrice** | float | 产品列表价 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUPhoneServerRenewPrice
&Region=cn-zj
&ProjectId=wxcfpqcB
&ServerId=weJEQOgD
&ChargeType=KZqcGylt
&CityId=wprICDeA
```

### 响应示例
    
```json
{
  "Action": "GetUPhoneServerRenewPriceResponse",
  "Message": "ERarYwVa",
  "PriceSet": [
    {
      "ChargeType": "WVqIDgvR",
      "ListPrice": 7.78461,
      "OriginalPrice": 3.71569,
      "Price": 8.51871
    }
  ],
  "RetCode": 0
}
```





