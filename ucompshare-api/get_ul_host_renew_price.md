# 获取主机续费价格 - GetULHostRenewPrice

## 简介

获取主机续费价格









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULHostRenewPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ULHostId** | string | ULHost实例ID |**Yes**|
| **ChargeType** | string | 计费类型。支持：Year/Month；默认：Month |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PriceSet** | array[[*ULHostPriceSet*](#ULHostPriceSet)] |  |**Yes**|

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
https://api.ucloud.cn/?Action=GetULHostRenewPrice
&Region=cn-zj
&ProjectId=SzlNcccn
&ULHostId=ZCoTNViV
&ChargeType=dCpoYPFr
```

### 响应示例
    
```json
{
  "Action": "GetULHostRenewPriceResponse",
  "PriceSet": [
    {
      "ChargeType": "LhnprcyJ",
      "ListPrice": 6.59751,
      "ListPriceDetail": {},
      "OriginalPrice": 9.54716,
      "OriginalPriceDetail": {},
      "Price": 5.37966,
      "PriceDetail": {}
    }
  ],
  "RetCode": 0
}
```





