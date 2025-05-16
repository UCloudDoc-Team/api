# 创建安全组规则 - CreateSecGroupRule

## 简介








## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateSecGroupRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateSecGroupRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **SecGroupId** | string | 需要添加规则的安全组资源ID。 |**Yes**|
| **Rule.N.Direction** | string |  "Ingress/Egress"，入站规则/出站规则  |**Yes**|
| **Rule.N.IPRange** | string | IP 地址信息，逗号分隔。 |**Yes**|
| **Rule.N.Priority** | int | 规则优先级。范围为 1\~200 |**Yes**|
| **Rule.N.ProtocolType** | string |  协议类型。"TCP","UDP","ICMP","ICMPv6","ALL" |**Yes**|
| **Rule.N.DstPort** | string | 目的端口。逗号分隔，如 "80,443"、"443,2000-10000" |**Yes**|
| **Rule.N.RuleAction** | string | 规则行为。"Accept" 或 "Drop" |**Yes**|
| **Rule.N.Remark** | string |  规则备注  |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RuleId** | array[string] | 规则 ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateSecGroupRule
&Region=cn-zj
&ProjectId=ALLXrNsN
&SecGroupId=sTCHnCkb
&Rule.n=qJSdTFWU
&Rule.n.IPRange=hfqrGIBI
&Rule.n.Priority=8
&Rule.n.ProtocolType=VrzyUOTd
&Rule.n.DstPort=ziuMdiRW
&Rule.n.RuleAction=HMYwyODF
&Rule.n.Remark=QPIwNwmO
```

### 响应示例
    
```json
{
  "Action": "CreateSecGroupRuleResponse",
  "RetCode": 0,
  "RuleId": [
    "HTZtyZHF"
  ]
}
```





