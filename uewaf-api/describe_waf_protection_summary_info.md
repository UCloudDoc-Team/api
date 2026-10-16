# 获取防护规则列表 - DescribeWafProtectionSummaryInfo

## 简介

获取防护规则列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafProtectionSummaryInfo`                        | **Yes** |
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
| **TotalCount** | int | 规则数量 |No|
| **WorkMode** | string | 工作模式 |No|
| **RuleSetList** | array[[*ProtectionSummaryRuleSetEntry*](#ProtectionSummaryRuleSetEntry)] | 规则集列表，参考ProtectionSummaryRuleSetEntry |No|

#### 数据模型


#### ProtectionSummaryRuleSetEntry

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RuleName** | string | 规则名称 |No|
| **RuleAction** | string | 规则动作 |No|
| **Priority** | int | 优先级 |No|
| **RiskRank** | string | 风险等级 |No|
| **RiskType** | string | 风险类型 |No|
| **RuleSetID** | int | 规则集ID |No|
| **RuleSetType** | string | 规则集类型 |No|
| **SysRuleset** | int | 规则集起始ID |No|
| **RuleDescription** | string | 规则描述 |No|
| **RuleList** | array[[*ProtectionSummaryRuleInfo*](#ProtectionSummaryRuleInfo)] | 规则详情，参考ProtectionSummaryRuleInfo |No|

#### ProtectionSummaryRuleInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Field** | string | 匹配字段 |No|
| **Operator** | string | 行为动作 |No|
| **Content** | string | 匹配内容 |No|
| **RuleId** | int | 规则ID |No|
| **Description** | string | 规则描述 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafProtectionSummaryInfo
&ProjectId=org-xxx
&FullDomain=www.test.com
```

### 响应示例
    
```json
{
  "Action": "DescribeWafProtectionSummaryInfoReponse",
  "RetCode": 0,
  "RuleSetList": [
    {
      "Location": "root",
      "Phase": "access",
      "Priority": 0,
      "RiskRank": "High",
      "RiskType": "scan",
      "RuleAction": "Deny",
      "RuleDescription": "",
      "RuleList": [
        {
          "Content": "2.2.2.2",
          "Description": "",
          "Field": "SrcIp",
          "Operator": "Contain",
          "RuleId": 45000,
          "UserRuleId": 45001
        }
      ],
      "RuleName": "test",
      "RuleSetID": 45000,
      "RuleSetType": "",
      "SysRuleset": 90045000
    }
  ],
  "TotalCount": 1,
  "WorkMode": "Alarm"
}
```





