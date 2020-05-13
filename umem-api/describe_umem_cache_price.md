# 获取umemcache组价格 - DescribeUMemcachePrice

## 简介

获取umemcache组价格信息





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUMemcachePrice)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUMemcachePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Size** | int | 容量大小,单位:GB 取值范围[1-32] |**Yes**|
| **ChargeType** | string | 计费模式，Year， Month， Dynamic，默认: Dynamic 默认: 获取所有计费模式的价格 |No|
| **Quantity** | int | 购买umemcache的时长，默认值为1 |No|
| **Type** | string | 空间类型:single(无热备),double(热备)(默认: double) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UMemcachePriceSet*](#UMemcachePriceSet)] | 价格列表, 参见 UMemcachePriceSet |No|

#### 数据模型


#### UMemcachePriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | 计费模式，Year, Month, Dynamic |No|
| **Price** | int | 总价格 |No|
| **ListPrice** | int | 产品列表价 |No|
| **OriginalPrice** | int | 原价 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUMemcachePrice
&Region=cn-bj2
&Zone=cn-bj2-04
&Size=1
&ProjectId=NKVlvLHl
&Type=uPFaYIFP
```

### 响应示例
    
```json
{
  "Action": "DescribeUMemcachePriceResponse",
  "DataSet": [
    {
      "ChargeType": "Year",
      "ListPrice": 54000,
      "OriginalPrice": 54000,
      "Price": 54000
    },
    {
      "ChargeType": "Month",
      "ListPrice": 5400,
      "OriginalPrice": 5400,
      "Price": 5400
    },
    {
      "ChargeType": "Dynamic",
      "ListPrice": 11,
      "OriginalPrice": 11,
      "Price": 11
    }
  ],
  "RetCode": 0
}
```





