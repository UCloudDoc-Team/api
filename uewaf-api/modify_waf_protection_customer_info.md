# 编辑自定义防护规则 - ModifyWafProtectionCustomerInfo

## 简介

编辑自定义防护规则









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyWafProtectionCustomerInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **RuleSetID** | int | 规则ID |**Yes**|
| **RuleName** | string | 规则名称 |**Yes**|
| **RiskRank** | string | 规则风险等级 |**Yes**|
| **RuleAction** | string | 规则匹配后的动作 |**Yes**|
| **RuleNum** | int | 规则匹配条件个数 |**Yes**|
| **RiskType** | string | 风险种类，scan,loopholes,xss,cc,sql,exec,webshell,infoleak,eaa,protocol,other |**Yes**|
| **FullDomain** | string | 域名， 域名与域名ID 必须选填一项 |**Yes**|
| **Rule** | string | 规则匹配条件 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyWafProtectionCustomerInfo
&ProjectId=org-xxx
&FullDomain=www.test.com
&RuleSetID=45000
&RuleName=test
&RiskRank=Low
&RuleAction=Deny
&RuleNum=1
&Rule.0=Field:SrcIp,Operator:Contain,Content:2.2.2.3
&RiskType=scan
```

### 响应示例
    
```json
{
  "Action": "ModifyWafProtectionCustomerInfoResponse",
  "RetCode": 0
}
```





