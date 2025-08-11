# 获取UPFS文件系统价格 - DescribeUPFSVolumePrice

## 简介

获取UPFS文件系统价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUPFSVolumePrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUPFSVolumePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Size** | int | 文件系统大小，单位为GB，新架构容量型最小容量为500GB，以100GB递增，最大不超过100TB。 |**Yes**|
| **Quantity** | int | 购买UPFS的时长， 默认为1 |No|
| **ChargeType** | string | Year， Month默认: Month |No|
| **VolumeId** | string | UPFS文件系统id，第一次创建文件系统时不需要传这个参数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UPFSPriceDataSet*](#UPFSPriceDataSet)] | upfs 价格信息 |No|

#### 数据模型


#### UPFSPriceDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | Year， Month |No|
| **Price** | float | 价格 (单位: 分) |No|
| **OriginalPrice** | float | 原价格 (单位: 分) |No|
| **ChargeName** | string | “upfs” |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUPFSVolumePrice
&Region=nBGbTxUa
&ProjectId=wrAsrDmQ
&Size=9
&StorageType=nzWXCeOf
&Quantity=4
&ChargeType=RKSdyKyy
&VolumeId=ErIzqNtu
```

### 响应示例
    
```json
{
  "Action": "DescribeUPFSVolumePriceResponse",
  "DataSet": [
    {
      "ChargeName": "pSGLBrph",
      "ChargeType": "MJjvvwUG",
      "OriginalPrice": 4.59432,
      "Price": 9.89657
    }
  ],
  "RetCode": 0
}
```





