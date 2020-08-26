# 取uredis价格信息 - DescribeURedisPrice

## 简介

取uredis价格信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeURedisPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeURedisPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Size** | int | 量大小,单位:GB  取值范围[1-32] |**Yes**|
| **ChargeType** | string | 计费模式，Year， Month， Dynamic；如果不指定，则一次性获取三种计费 |No|
| **Quantity** | int | 计费模式为Dynamic时，购买的时长, 默认为1 |No|
| **RegionFlag** | boolean | 是否是跨机房URedis(默认false) |No|
| **ProductType** | string | 产品类型：MS_Redis（标准主备版），S_Redis（从库），默认为MS_Redis |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*URedisPriceSet*](#URedisPriceSet)] | 价格 参数见 UMemPriceSet |No|

#### 数据模型


#### URedisPriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OriginalPrice** | int | 原价 |**Yes**|
| **ChargeType** | string | Year， Month， Dynamic，Trial |No|
| **ListPrice** | int | 产品列表价 |No|
| **Price** | int | 总价格 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeURedisPrice
&Region=cn-bj2
&Zone=cn-bj2-04
&Size=8
&Type=pYeMRrBb
```

### 响应示例
    
```json
{
  "Action": "DescribeURedisPriceResponse",
  "DataSet": [
    {
      "ChargeType": "Year",
      "ListPrice": 640000,
      "OriginalPrice": 640000,
      "Price": 640000
    },
    {
      "ChargeType": "Month",
      "ListPrice": 64000,
      "OriginalPrice": 64000,
      "Price": 64000
    },
    {
      "ChargeType": "Dynamic",
      "ListPrice": 136,
      "OriginalPrice": 136,
      "Price": 136
    }
  ],
  "RetCode": 0
}
```





