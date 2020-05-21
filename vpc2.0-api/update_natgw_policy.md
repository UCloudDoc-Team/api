# 更新NAT网关端口转发规则 - UpdateNATGWPolicy

## 简介

更新NAT网关端口转发规则






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateNATGWPolicy)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateNATGWPolicy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **NATGWId** | string | NAT网关Id |**Yes**|
| **PolicyId** | string | 转发策略Id |**Yes**|
| **Protocol** | string | 协议类型。枚举值为：TCP 、 UDP |**Yes**|
| **SrcEIPId** | string | 源IP。填写对应的EIP Id |**Yes**|
| **SrcPort** | string | 源端口。可填写固定端口，也可填写端口范围。支持的端口范围为1-6553 |**Yes**|
| **DstIP** | string | 目标IP。填写对饮的目标IP地址 |**Yes**|
| **DstPort** | string | 目标端口。可填写固定端口，也可填写端口范围。支持的端口范围为1-65535 |**Yes**|
| **PolicyName** | string | 转发策略名称。默认为空 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateNATGWPolicy
&Region=xxx
&ProjectId=xxx
&NATGWId=hgcVoyEy
&PolicyId=nfKIELvQ
&Protocol=TCP
&SrcEIPId=yuPOfoNO
&SrcPort=zUtgCzdK
&DstIp=NNWLPLlu
&DstPort=SOPruxNJ
&PolicyName=YTEVHszL
```

### 响应示例
    
```json
{
  "Action": "UpdateNATGWPolicyResponse",
  "RetCode": 0
}
```





