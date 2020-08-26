# 获取价格 - DescribeUMemPrice

## 简介

获取UMem实例价格信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUMemPrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUMemPrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **Size** | int | 购买umem大小,单位:GB,范围[1\~1024] |**Yes**|
| **Type** | string | 空间类型:single(无热备),double(热备)(默认: double) |**Yes**|
| **ChargeType** | string | Year， Month， Dynamic 如果不指定，则一次性获取三种计费 |No|
| **Quantity** | int | 购买UMem的时长，默认值为1 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UMemPriceSet*](#UMemPriceSet)] | 价格 参数见 UMemPriceSet |No|

#### 数据模型


#### UMemPriceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | Year， Month， Dynamic，Trial |No|
| **Price** | int | 现价 |No|
| **ListPrice** | int | 产品列表价 |No|
| **OriginalPrice** | int | 原价 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUMemPrice
&Region=cn-bj2
&Zone=cn-bj2-04
&Size=3
&Type=single
&RegionFlag=false
```

### 响应示例
    
```json
{
  "Action": "DescribeUMemPriceResponse",
  "DataSet": [
    {
      "ChargeType": "Year",
      "ListPrice": 120000,
      "OriginalPrice": 120000,
      "Price": 120000
    },
    {
      "ChargeType": "Month",
      "ListPrice": 12000,
      "OriginalPrice": 12000,
      "Price": 12000
    },
    {
      "ChargeType": "Dynamic",
      "ListPrice": 24,
      "OriginalPrice": 24,
      "Price": 24
    }
  ],
  "RetCode": 0
}
```





