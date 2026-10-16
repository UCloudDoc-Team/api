# 获取Nat网关的出口规则（SNAT规则） - DescribeSnatRule

## 简介

获取Nat网关的出口规则（SNAT规则）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeSnatRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSnatRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NATGWId** | string | NAT网关的ID |**Yes**|
| **SourceIp** | string | 需要出外网的私网IP地址，例如10.9.7.xx |No|
| **SnatIp** | string | EIP的ip地址,例如106.75.xx.xx |No|
| **Offset** | string | 偏移，默认为0 |No|
| **Limit** | string | 分页，默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*NATGWSnatRule*](#NATGWSnatRule)] | 某个NAT网关的所有Snat规则 |**Yes**|
| **TotalCount** | int | 规则数量 |**Yes**|

#### 数据模型


#### NATGWSnatRule

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SnatIp** | string | EIP地址，如106.76.xx.xx |**Yes**|
| **SourceIp** | string | 资源的内网IP地址 |**Yes**|
| **SubnetworkId** | string | SourceIp所属的子网id |**Yes**|
| **Name** | string | snat规则名称 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSnatRule
&NATGWId=UNWjzcHH
&Offset=koYtmbPl
&Limit=qTqZzcEW
```

### 响应示例
    
```json
{
  "Action": "DescribeSnatRuleResponse",
  "DataSet": [
    "VBENwtTq",
    "eJdgDwrm",
    "cttWRRWX",
    "LzamjxPo",
    "pXeuRpBP",
    "PKcCIcqJ"
  ],
  "RetCode": 0,
  "TotalCount": "ckUpWqAA"
}
```





