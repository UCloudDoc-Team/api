# 展示NAT网关端口转发规则 - DescribeNATGWPolicy

## 简介

展示NAT网关端口转发规则






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNATGWPolicy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNATGWPolicy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NATGWId** | string | NAT网关Id |**Yes**|
| **Limit** | int | 返回数据长度，默认为10000 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的转发策略总数 |**Yes**|
| **DataSet** | array[[*NATGWPolicyDataSet*](#NATGWPolicyDataSet)] | 查到的NATGW 转发策略的详细信息 |No|

#### 数据模型


#### NATGWPolicyDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NATGWId** | string | NAT网关Id |**Yes**|
| **PolicyId** | string | 转发策略Id |**Yes**|
| **Protocol** | string | 协议类型 |**Yes**|
| **SrcEIP** | string | 端口转发前端EIP |**Yes**|
| **SrcEIPId** | string | 端口转发前端EIP Id |**Yes**|
| **SrcPort** | string | 源端口 |**Yes**|
| **DstIP** | string | 目的地址 |**Yes**|
| **DstPort** | string | 目的端口 |**Yes**|
| **PolicyName** | string | 转发策略名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeNATGWPolicy
&Region=xxx
&ProjectId=xxx
&NATGWId=NdvawRZz
&Limit=1000
&Offset=0
```

### 响应示例
    
```json
{
  "Action": "DescribeNATGWPolicyResponse",
  "DataSet": [
    {
      "DstIP": "10.0.0.190",
      "DstPort": "80",
      "NATGWId": "natgw-anbgfu",
      "PolicyId": "policy-sh2Qhg",
      "PolicyName": "port_80",
      "Protocol": "TCP",
      "SrcEIP": "106.75.101.196",
      "SrcEIPId": "eip-aeeiew",
      "SrcPort": "80"
    },
    {
      "DstIP": "10.0.2.71",
      "DstPort": "0",
      "NATGWId": "natgw-anbgfu",
      "PolicyId": "policy-vQyaKW",
      "PolicyName": "port_81",
      "Protocol": "TCP",
      "SrcEIP": "106.75.101.196",
      "SrcEIPId": "eip-aeeiew",
      "SrcPort": "22"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





