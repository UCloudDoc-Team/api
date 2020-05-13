# 添加CC防御规则 - AddAntiCCRule

## 简介

添加CC防御规则





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddAntiCCRule)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddAntiCCRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Domain** | string | 要添加防护规则的域名 |**Yes**|
| **Reqs** | int | 统计时长内的请求数 |**Yes**|
| **URL** | string | uri，eg：/index.html |**Yes**|
| **Mode** | string | 匹配模式，equal:完全匹配；contains:包含 |**Yes**|
| **Duration** | int | 统计时长,单位： 秒 |**Yes**|
| **ActionType** | string | 匹配后执行的动作，forbidden:拦截请求；captcha:验证码； iptables：IP封堵 |**Yes**|
| **Validity** | int | 动作有效期，单位：分钟 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Id** | int | 添加成功后返回的规则ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddAntiCCRule
&ProjectId=org-xxx
&Domain=www.test.com
&Reqs=55000
&URL=/index.html
&Mode=equal
&Duration=2800
&ActionType=forbidden
&Validity=5720
```

### 响应示例
    
```json
{
  "Action": "AddAntiCCRuleResponse",
  "Id": 6,
  "RetCode": 0
}
```





