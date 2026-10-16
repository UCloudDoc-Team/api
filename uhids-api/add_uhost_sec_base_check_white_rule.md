# 添加安全基线白名单 - AddUHostSecBaseCheckWhiteRule

## 简介

添加安全基线白名单









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddUHostSecBaseCheckWhiteRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Data** | string | 基线白名单规则信息（值为以下字段的json转base64后字符串，json格式：{"Data":[{"IP":{"Type":"ip","IPs":["192.168.3.4","192.168.3.4"]},"RuleID":"B0101001V01","AppName":"Linux","Description":"存在弱口令用户[testUser]","RiskType":"配置缺陷","RiskLevel":"高危","User":"testUser"},{"IP":{"Type":"all","IPs":[]},"RuleID":"B0101001V01","AppName":"Linux","Description":"存在弱口令用户[testUser]","RiskType":"配置缺陷","RiskLevel":"高危","User":"testUser"}]}） |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Success** | int | 成功数 |No|
| **Fail** | int | 失败数 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddUHostSecBaseCheckWhiteRule
&ProjectId=hiNtPTZZ
&Data=fStRIBrd
```

### 响应示例
    
```json
{
  "Action": "AddUHostSecBaseCheckWhiteRuleResponse",
  "Fail": 1,
  "RetCode": 0,
  "Success": 3
}
```





