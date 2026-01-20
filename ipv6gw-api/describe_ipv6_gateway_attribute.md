# 查看ipv6网关详情 - DescribeIpv6GatewayAttribute

## 简介

查看指定ipv6网关详情, 该接口仅返回能开启公网带宽的ipv6信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeIpv6GatewayAttribute`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Ipv6GatewayId** | string | ipv6网关ID |**Yes**|
| **ObjectType** | string | ipv6地址绑定资源类型。传空则返回不按资源类型过滤。<br />枚举值:<br />"uhost" -> 云主机; <br />"uni" -> 虚拟网卡; <br />"alb" -> 应用型负载均衡; <br />"nlb" -> 网络型负载均衡 |No|
| **Offset** | int | 列表起始位置偏移量，默认值为0 |No|
| **Limit** | int | 返回数据长度，默认值为20，最大值为100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Ipv6GatewayId** | string | ipv6网关ID |No|
| **Name** | string | 名称 |No|
| **Tag** | string | 业务组 |No|
| **Remark** | string | 备注 |No|
| **VPCId** | string | vpc ID |No|
| **CreateTime** | int | 创建时间 |No|
| **TotalCount** | int | 总数 |No|
| **Ipv6AddressInfos** | array[[*IPv6AddressInfo*](#IPv6AddressInfo)] | 所有可出外网的ipv6地址信息 |No|

#### 数据模型


#### IPv6AddressInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ipv6AddressId** | string | ipv6地址ID |No|
| **Ipv6Address** | string | ipv6地址 |No|
| **SubnetId** | string | 子网ID |No|
| **PayMode** | string | 付费模式。枚举值：<br />"Bandwidth" -> 带宽计费 |No|
| **InternetBandwidthId** | string | ipv6外网带宽Id |No|
| **Bandwidth** | int | 带宽值 |No|
| **ObjectId** | string | 绑定的资源ID |No|
| **ObjectType** | string | 绑定对象资源类型 |No|
| **ObjectName** | string | 绑定对象名称 |No|
| **OperatorName** | string | 线路名称。<br />枚举值: <br />"ChinaMobile" -> 移动; <br />"BGP" -> BGP; <br />"Unicom" -> 联通; <br />"Telecom" -> 电信 |No|
| **ChargeType** | string | 收费类型 |No|
| **Status** | string | 状态。 <br />枚举值:<br />"Public" -> 已开启公网带宽; <br />"Normal" -> 未开启公网带宽 |No|
| **ExpireTime** | int | 过期时间 |No|
| **Expire** | string | 是否过期。 <br />枚举值: <br />"Expired" -> 过期; <br />"UnExpired" -> 未过期; <br />"UnKnown" -> 未知 |No|
| **AutoRenew** | string | 是否自动续费。<br />枚举值：<br />"Yes" -> 是; <br />"No" -> 否; <br />"UnKnown" -> 未知 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeIpv6GatewayAttribute
&Region=rus-mosc
&ProjectId=org-XXXXX
&Ipv6GatewayId=ipv6gw-XXXXX
&Offset=0
&Limit=1
&ObjectType=uni
&ObjectType=QPMChUGa
```

### 响应示例
    
```json
{
  "Action": "DescribeIpv6GatewayAttributeResponse",
  "CreateTime": 1746705316,
  "Ipv6AddressInfos": [
    {
      "AutoRenew": "Yes",
      "Bandwidth": 8,
      "ChargeType": "Month",
      "Expire": "UnExpired",
      "ExpireTime": 1770876838,
      "InternetBandwidthId": "ipv6bw-XXXXX",
      "Ipv6Address": "X:X:X:X:X:X:X:X",
      "Ipv6AddressId": "ipv6-XXXXX",
      "ObjectId": "uni-XXXXX",
      "ObjectName": "test",
      "ObjectType": "uni",
      "OperatorName": "Telecom",
      "PayMode": "Bandwidth",
      "Status": "Public",
      "SubnetId": "subnet-XXXXX"
    },
    {
      "AutoRenew": "UnKnown",
      "Bandwidth": 8,
      "ChargeType": "",
      "Expire": "UnKnown",
      "ExpireTime": 0,
      "InternetBandwidthId": "",
      "Ipv6Address": "X:X:X:X:X:X:X:X",
      "Ipv6AddressId": "ipv6-XXXXX",
      "ObjectId": "uni-XXXXX",
      "ObjectName": "test",
      "ObjectType": "uni",
      "OperatorName": "Telecom",
      "PayMode": "",
      "Status": "Normal",
      "SubnetId": "subnet-XXXXX"
    }
  ],
  "Ipv6GatewayId": "ipv6gw-XXXXX",
  "Name": "ipv6",
  "Remark": "apRVFumf",
  "RetCode": 0,
  "Tag": "Default",
  "TotalCount": 2,
  "VPCId": "uvnet-XXXXX"
}
```





