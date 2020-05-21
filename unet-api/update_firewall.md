# 更新防火墙规则 - UpdateFirewall

## 简介

更新防火墙规则



!> note<br />在更新防火墙规则时，新的规则会覆盖掉原有规则。所以若需要更改或加入新的规则，需要将原所有规则与新规则一起提交。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateFirewall)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateFirewall`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FWId** | string | 防火墙资源ID |**Yes**|
| **Rule.N** | string | 防火墙规则，例如：TCP\|22\|192.168.1.1/22\|DROP\|LOW\|禁用22端口，第一个参数代表协议：第二个参数代表端口号，第三个参数为ip，第四个参数为ACCEPT（接受）和DROP（拒绝），第五个参数优先级：HIGH（高），MEDIUM（中），LOW（低），第六个参数为该条规则的自定义备注 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **FWId** | string | 防火墙id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateFirewall
&ProjectId=org-xxx
&Region=xxxx
&FWId=fw-xxxx
&Rule.1=UDP|53|0.0.0.0/0|ACCEPT|HIGH|备注
&Rule.0=TCP|3306|0.0.0.0/0|DROP|HIGH|备注
```

### 响应示例
    
```json
{
  "Action": "UpdateFirewallResponse",
  "FWId": "firewall-xxx",
  "RetCode": 0
}
```





