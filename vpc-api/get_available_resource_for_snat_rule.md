# 获得可添加snat规则（出口规则）的资源列表 - GetAvailableResourceForSnatRule

## 简介

获取可用于添加snat规则（出口规则）的资源列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetAvailableResourceForSnatRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetAvailableResourceForSnatRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **NATGWId** | string | NAT网关Id |**Yes**|
| **Offset** | int | 数据偏移量, 默认为0 |No|
| **Limit** | int | 数据分页值, 默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*GetAvailableResourceForSnatRuleDataSet*](#GetAvailableResourceForSnatRuleDataSet)] | 返回的资源详细信息 |**Yes**|
| **TotalCount** | int | 总数 |**Yes**|

#### 数据模型


#### GetAvailableResourceForSnatRuleDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |No|
| **ResourceName** | string | 资源名称 |No|
| **PrivateIP** | string | 资源内网IP |No|
| **ResourceType** | string | 资源类型 |No|
| **SubnetworkId** | string | 资源所属VPC的ID |No|
| **VPCId** | string | 资源所属子网的ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetAvailableResourceForSnatRule
&Region=yyhASOAY
&ProjectId=UWaRmWcE
&NATGWId=XwXkQMAW
&Offset=2
&Limit=1
```

### 响应示例
    
```json
{
  "Action": "GetAvailableResourceForSnatRuleResponse",
  "DataSet": [
    {
      "PrivateIP": "uHuoyYFI",
      "ResourceId": "qXdXUnTs",
      "ResourceName": "TseFpSYi",
      "ResourceType": "uOcvcHeb",
      "SubnetworkId": "dmBHMzcz",
      "VPCId": "pzVhVEUB"
    },
    {
      "PrivateIP": "kxPAXSCn",
      "ResourceId": "JqMVhUhu",
      "ResourceName": "qoyOPJia",
      "ResourceType": "VqTetHsQ",
      "SubnetworkId": "BkrGxoip",
      "VPCId": "zBHWnLVr"
    },
    {
      "PrivateIP": "LVnKUGoN",
      "ResourceId": "XRrQUIbo",
      "ResourceName": "NSJCiYYr",
      "ResourceType": "CyXwCcqN",
      "SubnetworkId": "ZbsfHYSG",
      "VPCId": "eWCSjACm"
    },
    {
      "PrivateIP": "laqANTXC",
      "ResourceId": "dwdCkTls",
      "ResourceName": "TckJOsbL",
      "ResourceType": "fiZizgtR",
      "SubnetworkId": "GRpEqNJs",
      "VPCId": "kVEJGGak"
    },
    {
      "PrivateIP": "zmlVqWEt",
      "ResourceId": "KRkaFsvA",
      "ResourceName": "TdbSIpnW",
      "ResourceType": "DpNUxHHD",
      "SubnetworkId": "csUhLeYX",
      "VPCId": "dIvkrHDA"
    },
    {
      "PrivateIP": "YLAmlLKq",
      "ResourceId": "NdiwmcLU",
      "ResourceName": "fjzxuLRW",
      "ResourceType": "rxJeUYnO",
      "SubnetworkId": "nGnpcIsX",
      "VPCId": "EfWodcJo"
    },
    {
      "PrivateIP": "RGaCxTVB",
      "ResourceId": "cVcquAJG",
      "ResourceName": "dBMRGKCo",
      "ResourceType": "UMzQqjRh",
      "SubnetworkId": "llqWelBB",
      "VPCId": "nWKYxJzx"
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





