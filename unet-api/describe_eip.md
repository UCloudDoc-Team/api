# 获取弹性IP信息 - DescribeEIP

## 简介

获取弹性IP信息





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeEIP)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeEIP`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写 |No|
| **EIPIds.N** | string | 弹性IP的资源ID如果为空, 则返回当前 Region中符合条件的的所有EIP |No|
| **Offset** | int | 数据偏移量, 默认为0 |No|
| **Limit** | int | 数据分页值, 默认为20 |No|
| **IPs.N** | string | IP地址，支持通过ip查询，如果ip与EIP都传，会取并集查询 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的弹性IP总数 |No|
| **UnbindCount** | int | 未绑定的弹性IP总数 |No|
| **TotalBandwidth** | int | 满足条件的弹性IP带宽总和, 单位Mbps |No|
| **EIPSet** | array[[*UnetEIPSet*](#UnetEIPSet)] | 弹性IP列表, 每项参数详见 UnetEIPSet |No|

#### 数据模型


#### UnetEIPSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **EIPId** | string | 弹性IP的资源ID |No|
| **Weight** | int | 外网出口权重, 默认为50, 范围[0-100] |No|
| **BandwidthType** | int | 带宽模式, 枚举值为: 0: 非共享带宽模式, 1: 共享带宽模式 |No|
| **Bandwidth** | int | 弹性IP的带宽, 单位为Mbps, 当BandwidthType=1时, 该处显示为共享带宽值. 当BandwidthType=0时, 该处显示这个弹性IP的带宽. |No|
| **Status** | string | 弹性IP的资源绑定状态, 枚举值为: used: 已绑定, free: 未绑定, freeze: 已冻结 |No|
| **ChargeType** | string | 付费方式, 枚举值为: Year, 按年付费; Month, 按月付费; Dynamic, 按小时付费; Trial, 试用. 按小时付费和试用这两种付费模式需要开通权限. |No|
| **CreateTime** | int | 弹性IP的创建时间, 格式为Unix Timestamp |No|
| **ExpireTime** | int | 弹性IP的到期时间, 格式为Unix Timestamp |No|
| **Resource** | [*UnetEIPResourceSet*](#UnetEIPResourceSet) | 弹性IP的详细信息列表, 具体结构见下方 UnetEIPResourceSet |No|
| **EIPAddr** | array[[*UnetEIPAddrSet*](#UnetEIPAddrSet)] | 弹性IP的详细信息列表, 具体结构见下方 UnetEIPAddrSet |No|
| **Name** | string | 弹性IP的名称,缺省值为 "EIP" |No|
| **Tag** | string | 弹性IP的业务组标识, 缺省值为 "Default" |No|
| **Remark** | string | 弹性IP的备注, 缺省值为 "" |No|
| **PayMode** | string | 弹性IP的计费模式, 枚举值为: "Bandwidth", 带宽计费; "Traffic", 流量计费; "ShareBandwidth",共享带宽模式. 默认为 "Bandwidth". |No|
| **ShareBandwidthSet** | [*ShareBandwidthSet*](#ShareBandwidthSet) | 共享带宽信息 参见 ShareBandwidthSet |No|
| **Expire** | boolean | 弹性IP是否到期 |No|

#### UnetEIPResourceSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceType** | string | 已绑定的资源类型, 枚举值为: uhost, 云主机；natgw：NAT网关；ulb：负载均衡器；upm: 物理机; hadoophost: 大数据集群;fortresshost：堡垒机；udockhost：容器；udhost：私有专区主机；vpngw：IPSec VPN；ucdr：云灾备；dbaudit：数据库审计，uni：虚拟网卡。 |No|
| **ResourceName** | string | 已绑定的资源名称 |No|
| **ResourceID** | string | 已绑定资源的资源ID |No|
| **SubResourceType** | string | 资源绑定的虚拟网卡的类型。uni，虚拟网卡。 |No|
| **SubResourceName** | string | 资源绑定的虚拟网卡的名称 |No|
| **SubResourceId** | string | 资源绑定的虚拟网卡的ID |No|
| **EIPId** | string | 弹性IP的资源ID |No|

#### UnetEIPAddrSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **OperatorName** | string | 运营商信息如: 国际: International, BGP: BGP |No|
| **IP** | string | IP地址 |No|

#### ShareBandwidthSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ShareBandwidth** | int | 共享带宽带宽值 |No|
| **ShareBandwidthName** | string | 共享带宽的资源名称 |No|
| **ShareBandwidthId** | string | 共享带宽ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeEIP
&Region=cn-bj2
&EIPIds.0=eip-XXXXX
&IPs.n=XXHDIxmf
```

### 响应示例
    
```json
{
  "Action": "DescribeEIPResponse",
  "EIPSet": [
    {
      "Bandwidth": 20,
      "BandwidthType": 1,
      "ChargeType": "Month",
      "CreateTime": 1528785841,
      "EIPAddr": [
        {
          "IP": "106.75.XX.XX",
          "OperatorName": "BGP"
        }
      ],
      "EIPId": "eip-XXXXX",
      "Expire": false,
      "ExpireTime": 1530374400,
      "Name": "EIP",
      "PayMode": "ShareBandwidth",
      "Remark": "",
      "Resource": {
        "ResourceID": "uhost-XXXXXX",
        "ResourceName": "test",
        "ResourceType": "uhost",
        "Zone": "cn-sh2-01"
      },
      "ShareBandwidthSet": {
        "ShareBandwidth": 20,
        "ShareBandwidthId": "bwshare-XXXX",
        "ShareBandwidthName": "test"
      },
      "Status": "used",
      "Tag": "Default",
      "Weight": 50
    }
  ],
  "Request_uuid": "f33cf273-89ed-4215-a9c6-XXXXXXX",
  "RetCode": 0,
  "TotalBandwidth": 13,
  "TotalCount": 10,
  "UnbindCount": 5
}
```





