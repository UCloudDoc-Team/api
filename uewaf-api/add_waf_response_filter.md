# 添加信息安全过滤规则 - AddWafResponseFilter

## 简介

添加信息安全过滤规则









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddWafResponseFilter`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 要添加规则的域名 |**Yes**|
| **Name** | string | 规则名称 |**Yes**|
| **Type** | string | 过滤类型；可选项：Status（状态码），Sensitive（敏感内容），Customize（自定义字符串）。 |**Yes**|
| **RuleAction** | string | 丢弃响应或伪装内容；可选项：DROP（丢弃响应），DISGUISE（伪装内容） |**Yes**|
| **Content** | string | 过滤内容。当过滤类型为Sensitive时为可选项，可选值：Identity（身份证号），TelNum（手机号），Email（邮件），BankNum（银行卡号） |No|
| **DisguiseFile** | string | 伪装响应内容 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ID** | int | 添加的规则ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddWafResponseFilter
&ProjectId=org-xxx
&FullDomain=www.test.com
&Name=test
&Type=Status
&Content=404
&RuleAction=DROP
```

### 响应示例
    
```json
{
  "Action": "AddWafResponseFilterResponse",
  "ID": 2,
  "RetCode": 0
}
```





