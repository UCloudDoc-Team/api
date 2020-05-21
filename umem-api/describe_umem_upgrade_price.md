# 获取升级价格 - DescribeUMemUpgradePrice

## 简介

获取UMem升级价格信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUMemUpgradePrice)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUMemUpgradePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Size** | int | 购买UMem大小,单位:GB |**Yes**|
| **Type** | string | 空间类型:single(无热备),double(热备)(默认: double) |**Yes**|
| **SpaceId** | string | 需要升级的空间的SpaceId |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | int | 价格(兼容老版本) |No|
| **DataSet** | [*PriceDataSet*](#PriceDataSet) | 价格 |No|

#### 数据模型


#### PriceDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TotalPrice** | int | 升降级资源的价格 |No|
| **CustomPrice** | int | 用户折后价 |No|
| **PurchaseValue** | int | 资源有效期 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUMemUpgradePrice
&Region=cn-bj2
&Zone=
&Size=16
&Type=double
&SpaceId=umem-mXXXX
```

### 响应示例
    
```json
{
  "Action": "DescribeUMemUpgradePriceResponse",
  "DataSet": {},
  "Price": 4,
  "RetCode": 0
}
```





