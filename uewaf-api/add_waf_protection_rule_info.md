# 添加WAF防护规则 - AddWafProtectionRuleInfo

## 简介

添加WAF防护规则








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddWafProtectionRuleInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 	<br />项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **RuleNum** | int | 规则匹配条件个数 |**Yes**|
| **RuleName** | string | 规则名称 |**Yes**|
| **RuleAction** | string | 规则命中之后的动作，Deny:拦截，Accept |**Yes**|
| **RiskRank** | string | 风险等级，Low:低,Middle:中,High:高 |**Yes**|
| **Rule.N** | string | 规则匹配条件，举例：Field:UserAgent,Operator:Contain,Content:xxxx |**Yes**|
| **FullDomain** | string | 要添加防护规则的域名 |**Yes**|
| **RiskType** | string | 风险种类；可选值：scan,loopholes,xss,cc,sql,exec,webshell,infoleak,eaa,protocol,other |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Id** | int | 添加成功后返回的防护规则ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddWafProtectionRuleInfo
&ProjectId=org-xxx
&FullDomain=www.test.com
&RuleNum=1
&RuleName=test
&RuleAction=Deny
&RiskRank=Low
&RiskType=scan
&Rule.0=Field:SrcIp,Operator:Contain,Content:2.2.2.2
```

### 响应示例
    
```json
{
  "Action": "AddWafProtectionRuleInfoResponse",
  "Id": 9,
  "RetCode": 0
}
```





