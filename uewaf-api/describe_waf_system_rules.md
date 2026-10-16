# 查询指定域名的系统默认规则 - DescribeWafSystemRules

## 简介

查询指定域名的系统默认规则









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafSystemRules`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 要查询的域名 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Rules** | array[[*SystemRuleInfo*](#SystemRuleInfo)] | 规则内容列表，参考SystemRuleInfo |No|

#### 数据模型


#### SystemRuleInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SysRuleset** | int | 规则起始编号 |No|
| **Action** | string | 动作 |No|
| **RiskRank** | string | 风险等级 |No|
| **RulesetType** | string | 规则集类型 |No|
| **Priority** | int | 优先级 |No|
| **AttackType** | string | 攻击类型 |No|
| **Description** | string | 规则描述 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafSystemRules
&ProjectId=org-xxx
&FullDomain=www.test.com
```

### 响应示例
    
```json
{
  "Action": "DescribeWafSystemRulesResponse",
  "RetCode": 0,
  "Rules": [
    {
      "Action": "ACCEPT",
      "AttackType": "default",
      "Description": "默认放行-未做归类",
      "Priority": 1,
      "RiskRank": "high",
      "RulesetType": "system",
      "SysRuleset": 10000
    }
  ]
}
```





