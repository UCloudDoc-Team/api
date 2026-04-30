# 查询筛选选项 - GetFilterOptions

## 简介

查询可用于订单筛选的资源、模型、地域等选项列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetFilterOptions)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetFilterOptions`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProductCode** | string | 产品类型（单选，可选），枚举值：`modelverse`、`sandbox`；为空时返回所有产品下的选项 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ResourceIds** | array[[*FilterOptionAiBill*](#FilterOptionAiBill)] | 资源选项列表 |**Yes**|
| **Models** | array[[*FilterOptionAiBill*](#FilterOptionAiBill)] | 模型选项列表 |No|
| **Dimensions** | array[[*FilterOptionAiBill*](#FilterOptionAiBill)] | 账单维度选项列表 |No|
| **PricingUnits** | array[[*FilterOptionAiBill*](#FilterOptionAiBill)] | 计费单位选项列表 |No|
| **Regions** | array[[*FilterOptionAiBill*](#FilterOptionAiBill)] | 地域选项列表 |No|
| **ProductCodes** | array[[*FilterOptionAiBill*](#FilterOptionAiBill)] | 产品类型选项列表 |No|
| **Projects** | array[[*FilterOptionAiBill*](#FilterOptionAiBill)] | 项目选项列表 |No|
| **PricingSKUs** | array[[*FilterOptionAiBill*](#FilterOptionAiBill)] | 计费 SKU 选项列表 |No|

#### 数据模型


#### FilterOptionAiBill

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string | 显示名称 |No|
| **Value** | object | 值实际是interface |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetFilterOptions
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=KOvuFbMW
&ProductCode=rjAIcPrn
```

### 响应示例
    
```json
{
  "Action": "GetFilterOptionsResponse",
  "Data": {},
  "Dimensions": [
    {
      "Name": "XtBSHSoJ",
      "Value": "WgZmMQOo"
    }
  ],
  "Models": [
    {
      "Name": "kqJMJdxD",
      "Value": "gxiRtfIw"
    }
  ],
  "PricingSKUs": "qgNjqply",
  "PricingUnits": [
    {
      "Name": "MoqIBNBK",
      "Value": "yJfochKY"
    }
  ],
  "ProductCodes": "nmkSUkVh",
  "Projects": "tEWWkBoj",
  "Regions": "nBOVDUOg",
  "RetCode": 0
}
```





