# 创建防火墙 - CreateFirewall

## 简介

创建防火墙






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateFirewall)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateFirewall`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写 |No|
| **Rule.N** | string | 防火墙规则，例如：TCP\|22\|192.168.1.1/22\|DROP\|LOW\|禁用22端口，第一个参数代表协议：第二个参数代表端口号，第三个参数为ip，第四个参数为ACCEPT（接受）和DROP（拒绝），第五个参数优先级：HIGH（高），MEDIUM（中），LOW（低），第六个参数为该条规则的自定义备注,bj1不支持添加备注 |**Yes**|
| **Name** | string | 防火墙名称 |**Yes**|
| **Tag** | string | 防火墙业务组，默认为Default |No|
| **Remark** | string | 防火墙描述，默认为空 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **FWId** | string | 防火墙ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateFirewall
&ProjectId=org-XXXX
&Region=cn-north
&Name=NewFirewall
&Tag=Default
&Rule.0=UDP|53|0.0.0.0/0|ACCEPT|HIGH|备注
&Rule.1=TCP|0-56636|0.0.0.0/0|ACCEPT|HIGH|备注
&Rule.2=TCP|3306|0.0.0.0/0|DROP|HIGH|备注
```

### 响应示例
    
```json
{
  "Action": "CreateFirewallResponse",
  "FWId": "dzPBwJgP",
  "RetCode": 0
}
```





