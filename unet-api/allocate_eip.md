# 申请弹性IP - AllocateEIP

## 简介

根据提供信息, 申请弹性IP






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AllocateEIP)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AllocateEIP`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。  |No|
| **OperatorName** | string | 弹性IP线路，枚举值：国际线路， International；BGP线路：Bgp；精品BGP：BGPPro。<br /><br />使用BGP线路的地域：北京二、上海金融云、上海二、广州等，其他地域均使用国际线路。<br />使用BGPPro线路的地域：香港 |**Yes**|
| **Bandwidth** | int | 弹性IP的外网带宽, 单位为Mbps. 共享带宽模式必须指定0M带宽, 非共享带宽模式必须指定非0Mbps带宽. 各地域非共享带宽的带宽范围如下： 流量计费[1-300]，带宽计费[1-10000] |**Yes**|
| **Tag** | string | 业务组名称, 默认为 "Default" |No|
| **ChargeType** | string | 付费方式, 枚举值为: Year, 按年付费; Month, 按月付费; Dynamic, 按时付费，默认为按月付费。 |No|
| **Quantity** | int | 购买的时长, 默认: 1 |No|
| **PayMode** | string | 弹性IP的计费模式. 枚举值: "Traffic", 流量计费; "Bandwidth", 带宽计费; "ShareBandwidth",共享带宽模式. 默认为 "Bandwidth".“PostAccurateBandwidth”：带宽后付费模式 |No|
| **ShareBandwidthId** | string | 绑定的共享带宽Id,仅当PayMode为ShareBandwidth时有效 |No|
| **Name** | string | 弹性IP的名称, 默认为 "EIP" |No|
| **Count** | int | 购买EIP数量，默认值为1 |No|
| **Remark** | string | 弹性IP的备注, 默认为空 |No|
| **CouponId** | string | 代金券ID, 默认不使用 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **EIPSet** | array[[*UnetAllocateEIPSet*](#UnetAllocateEIPSet)] | 申请到的EIP资源详情 参见 UnetAllocateEIPSet |No|

#### 数据模型


#### UnetAllocateEIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **EIPId** | string | 申请到的EIP资源ID |No|
| **EIPAddr** | array[[*UnetEIPAddrSet*](#UnetEIPAddrSet)] | 申请到的IPv4地址.  |No|

#### UnetEIPAddrSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OperatorName** | string | 运营商信息如: 国际: International, BGP: BGP |No|
| **IP** | string | IP地址 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AllocateEIP
&Bandwidth=2
&Tag=test
&PayMode=Bandwidth
&OperatorName=Bgp
&ChargeType=Month
&Region=cn-bj2
&UseType=GbJSTTUJ
&Count=7
```

### 响应示例
    
```json
{
  "Action": "AllocateEIPResponse",
  "EIPSet": [
    {
      "EIPAddr": [
        {
          "IP": "123.55.55.55",
          "OperatorName": "BGP"
        }
      ],
      "EIPId": "eip-nthrdr"
    }
  ],
  "RetCode": "0"
}
```





