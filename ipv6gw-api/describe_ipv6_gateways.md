# ipv6网关列表 - DescribeIpv6Gateways

## 简介

ipv6网关列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeIpv6Gateways)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeIpv6Gateways`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **VPCId** | string | vpc ID |No|
| **Ipv6GatewayIds.N** | string | ipv6网关ID列表，最大长度为20。指定Ipv6GatewayIds查询时，将忽略其他条件 |No|
| **Offset** | int | 列表起始位置偏移量，默认值为0 |No|
| **Limit** | int | 返回数据长度，默认值为20，最大值为100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | Ipv6Gateway总数。指定Ipv6GatewayIds / VPCId时，返回数量受限 |No|
| **Ipv6GatewayInfos** | array[[*IPv6GateWayInfo*](#IPv6GateWayInfo)] | ipv6网关信息列表 |No|

#### 数据模型


#### IPv6GateWayInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ipv6GatewayId** | string | ipv6 网关 ID |No|
| **VPCId** | string | vpc ID |No|
| **Name** | string | 名称 |No|
| **Tag** | string | 业务组 |No|
| **Remark** | string | 备注 |No|
| **CreateTime** | int | 创建时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeIpv6Gateways
&Region=cn-bj2
&ProjectId=org-XXXXX
&VPCId=uvnet-XXXXX
&Offset=0
&Limit=3
```

### 响应示例
    
```json
{
  "Action": "DescribeIpv6GatewaysResponse",
  "Ipv6GatewayInfos": [
    {
      "CreateTime": 1746705316,
      "Ipv6GatewayId": "ipv6gw-XXXXX",
      "Name": "ipv6",
      "Remark": "test",
      "Tag": "Default",
      "VPCId": "uvnet-XXXXX"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





