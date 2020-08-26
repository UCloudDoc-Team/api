# 获取带宽包信息 - DescribeBandwidthPackage

## 简介

获取某地域下的带宽包信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeBandwidthPackage)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeBandwidthPackage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Limit** | int | 返回数据分页值, 取值范围为 [0,10000000] 之间的整数, 默认为20 |No|
| **Offset** | int | 返回数据偏移量, 默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的带宽包总数 |No|
| **DataSets** | array[[*UnetBandwidthPackageSet*](#UnetBandwidthPackageSet)] | 带宽包详细信息, 参见 UnetBandwidthPackageSet |No|

#### 数据模型


#### UnetBandwidthPackageSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BandwidthPackageId** | string | 带宽包的资源ID |No|
| **EnableTime** | int | 生效时间, 格式为 Unix Timestamp |No|
| **DisableTime** | int | 失效时间, 格式为 Unix Timestamp |No|
| **CreateTime** | int | 创建时间, 格式为 Unix Timestamp |No|
| **Bandwidth** | int | 带宽包的临时带宽值, 单位Mbps |No|
| **EIPId** | string | 带宽包所绑定弹性IP的资源ID |No|
| **EIPAddr** | array[[*EIPAddrSet*](#EIPAddrSet)] | 带宽包所绑定弹性IP的详细信息,只有当EIPId对应双线IP时, EIPAddr的长度为2, 其他情况, EIPAddr长度均为1.参见 EIPAddrSet |No|

#### EIPAddrSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OperatorName** | string | 运营商信息, 枚举值为:  BGP: BGP; International: 国际. |No|
| **IP** | string | 弹性IP地址 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeBandwidthPackage
&Region=cn-bj2
```

### 响应示例
    
```json
{
  "Action": "DescribeBandwidthPackageResponse",
  "DataSets": [
    {
      "Bandwidth": 200,
      "BandwidthPackageID": "bwpack-XXXXXX",
      "CreateTime": 1430990525,
      "DisableTime": 1430997725,
      "EIPAddr": [
        {
          "IP": "123.59.XX.XX",
          "OperatorName": "BGP"
        }
      ],
      "EIPId": "eip-XXXXX",
      "EnableTime": 1430990525
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





