# 修改CC防御规则 - ModifyAntiCCRule

## 简介

修改CC防御规则









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyAntiCCRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **ID** | int | 要修改的规则ID |**Yes**|
| **Reqs** | int | 统计时长内请求次数 |**Yes**|
| **URL** | string | 请求的uri |**Yes**|
| **Mode** | string | URI匹配模式，equal:完全匹配;,contains:包含; |**Yes**|
| **Duration** | int | 统计时长,单位：秒 |**Yes**|
| **ActionType** | string | 触发条件后执行的动作，forbidden:拦截请求； captcha:验证码；iptables：IP封堵 |**Yes**|
| **Validity** | int | 动作有效期，单位：分钟 |**Yes**|
| **Domain** | string | 添加CC防护规则的域名 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyAntiCCRule
&ProjectId=org-xxx
&ID=44451
&Domain=www.test.com
&Reqs=100
&URL=/index.html
&Mode=equal
&Duration=60
&ActionType=forbidden
&Validity=60
```

### 响应示例
    
```json
{
  "Action": "ModifyAntiCCRuleResponse",
  "RetCode": 0
}
```





