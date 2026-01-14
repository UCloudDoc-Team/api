# 获取共享带宽信息 - DescribeShareBandwidth

## 简介

获取共享带宽信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeShareBandwidth)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeShareBandwidth`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ShareBandwidthIds.N** | string | 需要返回的共享带宽Id |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UnetShareBandwidthSet*](#UnetShareBandwidthSet)] | 共享带宽信息组 参见 UnetShareBandwidthSet |No|
| **TotalCount** | int | 符合条件的共享带宽总数，大于等于返回DataSet长度 |No|

#### 数据模型


#### UnetShareBandwidthSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IPVersion** | string | 共享带宽类型 |**Yes**|
| **ShareBandwidth** | int | 共享带宽值(预付费)/共享带宽峰值(后付费), 单位Mbps |No|
| **ShareBandwidthId** | string | 共享带宽的资源ID |No|
| **ChargeType** | string | 付费方式, 预付费:Year 按年,Month 按月,Dynamic 按时;后付费:PostPay(按月) |No|
| **CreateTime** | int | 创建时间, 格式为Unix Timestamp |No|
| **ExpireTime** | int | 过期时间, 格式为Unix Timestamp |No|
| **EIPSet** | array[[*EIPSetData*](#EIPSetData)] | EIP信息,详情见 EIPSetData |No|
| **Name** | string | 共享带宽名称 |No|
| **Tag** | string | 共享带宽的业务组标识, 缺省值为 "Default" |No|
| **LimitType** | string | 共享带宽限速类型; 枚举值: "Normal", "SpeedLimit" |No|
| **AutoRenew** | string | 共享带宽是否开启自动续费；是否开启自动续费；枚举值:"Yes","No" |No|
| **OperatorName** | string | 共享带宽的线路名称 |No|

#### EIPSetData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Bandwidth** | int | EIP带宽值 |No|
| **EIPAddr** | array[[*EIPAddrSet*](#EIPAddrSet)] | EIP的IP信息，详情见EIPAddrSet |No|
| **EIPId** | string | EIP资源Id |No|
| **FollowShareBandwidth** | boolean | 是否开启EIP跟随共享带宽模式；绑定普通共享带宽和限速开启跟随的场景，FollowShareBandwidth为true，其余场景为false |No|

#### EIPAddrSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OperatorName** | string | 运营商信息, 枚举值为:  BGP: BGP; International: 国际. |No|
| **IP** | string | 弹性IP地址 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeShareBandwidth
&Region=cn-bj2
```

### 响应示例
    
```json
{
  "Action": "DescribeShareBandwidthResponse",
  "DataSet": [
    {
      "ChargeType": "Dynamic",
      "CreateTime": 1529660427,
      "EIPSet": [
        {
          "Bandwidth": 1000,
          "EIPAddr": [
            {
              "IP": "106.75.XX.XX",
              "OperatorName": "BGP"
            }
          ],
          "EIPId": "eip-XXXXX"
        }
      ],
      "ExpireTime": 1529898027,
      "Name": "test",
      "ShareBandwidth": 20,
      "ShareBandwidthId": "bwshare-XXXX"
    }
  ],
  "Request_uuid": "a36b7aec-3911-4096-9110-XXXXX",
  "RetCode": 0,
  "TotalCount": 1,
  "TotolCount": 2
}
```





