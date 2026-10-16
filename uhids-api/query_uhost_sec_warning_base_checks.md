# 查询正在告警的安全基线类型列表 - QueryUHostSecWarningBaseChecks

## 简介

查询正在告警的安全基线类型列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryUHostSecWarningBaseChecks`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Type** | string | 过滤BaseCheck告警类型，sys:系统安全检查，app:应用安全检查 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | array[[*BaseCheckWarning*](#BaseCheckWarning)] | 正在告警基线类型 |No|

#### 数据模型


#### BaseCheckWarning

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RuleID** | string | 基线规则ID |No|
| **AppName** | string | 应用类 |No|
| **Description** | string | 风险描述 |No|
| **DescriptionEn** | string | 风险英文描述 |No|
| **RiskType** | string | 风险类型 |No|
| **RiskLevel** | string | 风险等级 |No|
| **AgentCount** | int | 影响主机数 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryUHostSecWarningBaseChecks
&ProjectId=vqnHcpTF
&TypeFilter=mBtLDfnV
&Type=OoaIlTjV
```

### 响应示例
    
```json
{
  "Action": "QueryUHostSecWarningBaseChecksResponse",
  "Result": [
    {
      "AppName": "FOSoENuh",
      "Description": "tmFHJsLG",
      "RiskLevel": "eRiPtSTP",
      "RiskType": "HJUZCfeh",
      "RuleID": "oNQkIZcx",
      "User": "zYCZniLN"
    }
  ],
  "RetCode": 0
}
```





