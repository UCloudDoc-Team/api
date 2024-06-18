# 获取升级价格 - DescribeUMemUpgradePrice

## 简介

获取UMem升级价格信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUMemUpgradePrice)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


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
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Size** | int | 购买UMem大小,单位:GB |**Yes**|
| **Type** | string | 空间类型:single(无热备),double(热备)(默认: double) |**Yes**|
| **SpaceId** | string | 需要升级的空间的SpaceId |**Yes**|
| **HighPerformance** | string | 是否为性能增强型。默认为false，或者不填，true为性能增强型。 |No|
| **IsSplit** | string | 如果是拆分按钮查询价格就填 true, 否则就填 false,默认为 false |No|
| **BlockIds.N** | string | 进行容量调整分片的分片ID(性能增强型不需要传入) |No|
| **BlockSize.N** | int | 进行容量调整的分片的目标容量,单位 GB<br />(性能增强型不需要传入) |No|
| **ProxyId** | string |  代理id |No|
| **NewCPU** | int | 代理升级后CPU核数 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Price** | int | 价格 |No|
| **OriginalPrice** | int | 原价 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUMemUpgradePrice
&Region=OYdDMZXj
&Zone=eOtEEIHT
&ProjectId=xaZfeoNa
&Size=6
&Type=bmNycqFN
&SpaceId=AmSgNavR
&HighPerformance=gPcaNcLQ
&IsSplit=AjafPGzg
&BlockIds.n=WJNZdGqo
&BlockSize.n=4
&ProxyId=SPUoFZMN
&NewCPU=1
```

### 响应示例
    
```json
{
  "Action": "DescribeUMemUpgradePriceResponse",
  "OriginalPrice": 9,
  "Price": 9,
  "RetCode": 0
}
```





