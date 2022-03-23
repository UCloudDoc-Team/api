# 获取文件系统价格 - DescribeUFSVolumePrice

## 简介

获取文件系统价格






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUFSVolumePrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUFSVolumePrice`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Size** | int | 文件系统大小，单位为GB，新架构容量型最小容量为500GB，以100GB递增，最大不超过100TB。新架构性能型最小容量为100GB，以100GB递增，最大不超过20TB |**Yes**|
| **StorageType** | string | 文件存储类型，枚举值，Basic表示容量型产品，Advanced表示性能型产品 |**Yes**|
| **Quantity** | int | 购买UFS的时长， 默认为1 |No|
| **ChargeType** | string | Year， Month， Dynamic，Trial，默认: Dynamic |No|
| **VolumeId** | string | 文件系统id，第一次创建文件系统时不需要传这个参数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UFSPriceDataSet*](#UFSPriceDataSet)] | ufs 价格信息 |No|

#### 数据模型


#### UFSPriceDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ChargeType** | string | Year， Month， Dynamic，Trial |No|
| **Price** | float | 价格 (单位: 分) |No|
| **ChargeName** | string | “UFS” |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUFSVolumePrice
&Region=HkdKBREf
&ProjectId=HyOvhXKd
&VolumeId=mSHMSuBe
&Quantity=4
&ChargeType=MFWpWMwK
&Size=4
&StorageType=xShMEetE
&VolumeId=BtpJrIyu
```

### 响应示例
    
```json
{
  "Action": "DescribeUFSVolumePriceResponse",
  "DataSet": [
    {
      "ChargeName": "yvhXFwCh",
      "ChargeType": "nKQKsuXt",
      "Price": 6.44823
    },
    {
      "ChargeName": "iEWvdvlO",
      "ChargeType": "eBXtSMgF",
      "Price": 6.42198
    },
    {
      "ChargeName": "ZXIRydLJ",
      "ChargeType": "gkeWHmzv",
      "Price": 2.77386
    },
    {
      "ChargeName": "FSmrJaPr",
      "ChargeType": "kpXKyKRm",
      "Price": 6.12148
    },
    {
      "ChargeName": "ysjFPvpx",
      "ChargeType": "obfbmFck",
      "Price": 3.62132
    },
    {
      "ChargeName": "msTwFsHQ",
      "ChargeType": "lrVWPQZt",
      "Price": 8.42654
    }
  ],
  "RetCode": 0
}
```





