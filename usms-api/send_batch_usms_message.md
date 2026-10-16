# 批量发送短信 - SendBatchUSMSMessage

## 简介

调用SendBatchUSMSMessage接口批量发送短信

?> 支持在一次请求中向多个不同的手机号码发送不同内容的短消息

!> 在一次批量请求中，最多支持200个号码


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=SendBatchUSMSMessage)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SendBatchUSMSMessage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **TaskContent** | string | 批量发送内容，该参数是json数组的base64编码结果。发送内容json数组中，每个“模板+签名”组合作为一个子项，每个子项内支持多个号码，<br />示例：<br />发送内容json数组（base64编码前）：[{"TemplateId": "UTA20212831C85C", "SigContent": "UCloud", "Target": [{"TemplateParams": ["123456"], "Phone": "18500000123", "ExtendCode": "123", "UserId": "456"} ] } ]   。json数组中各参数的定义："TemplateId":模板ID，"SigContent"短信签名内容，"Target"具体到号码粒度的发送内容。"Target"中的具体字段有："TemplateParams"实际发送的模板参数（若使用的是无参数模板，该参数不能传值），"Phone"手机号码, "ExtendCode"短信扩展码, "UserId"自定义业务标识ID。其中必传参数为"TemplateId", "SigContent", "Target"（"Target"中必传参数为"Phone"）。<br />实际调用本接口时TaskContent传值（发送内容base64编码后）为：W3siVGVtcGxhdGVJZCI6ICJVVEEyMDIxMjgzMUM4NUMiLCAiU2lnQ29udGVudCI6ICJVQ2xvdWQiLCAiVGFyZ2V0IjogW3siVGVtcGxhdGVQYXJhbXMiOiBbIjEyMzQ1NiJdLCAiUGhvbmUiOiAiMTg1MDAwMDAxMjMiLCAiRXh0ZW5kQ29kZSI6ICIxMjMiLCAiVXNlcklkIjogIjQ1NiJ9IF0gfSBdIA==      |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SessionNo** | string | 本次提交发送任务的唯一ID，可根据该值查询本次发送的短信列表。注：成功提交短信数大于0时，才返回该字段 |No|
| **ReqUuid** | string | 本次请求Uuid |No|
| **SuccessCount** | int | 成功提交短信（未拆分）条数 |No|
| **FailContent** | array[[*BatchInfo*](#BatchInfo)] | 未发送成功的详情，返回码非0时该字段有效，可根据该字段数据重发 |No|

#### 数据模型


#### BatchInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TemplateId** | string | 模板ID |**Yes**|
| **SigContent** | string | 签名 |**Yes**|
| **Target** | array[[*FailPhoneDetail*](#FailPhoneDetail)] | 具体号码信息 |**Yes**|
| **FailureDetails** | string | 未能成功发送的详情。注：模板/签名检验失败时，该字段有效 |No|

#### FailPhoneDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TemplateParams** | array[string] | 模板参数 |**Yes**|
| **Phone** | string | 手机号 |**Yes**|
| **ExtendCode** | string | 扩展号码 |No|
| **UserId** | string | 用户自定义ID |No|
| **FailureDetails** | string | 发送失败原因。注：若模板/签名校验失败，该字段为空 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SendBatchUSMSMessage
&PublicKey=vsRhB0Qzo9elXXXXXkw8o/vmss8Tb0vxi74A=
&Signature=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
&ProjectId=org1234
&TaskContent=WwogICAgewogICAgICAgICJUZW1wbGF0ZUlkIjoiVVRBMjAyMTI4MzFDODVDIiwKICAgICAgICAiU2lnQ29udGVudCI6IlVDbG91ZCIsCiAgICAgICAgIlRhcmdldCI6WwogICAgICAgICAgICB7CiAgICAgICAgICAgICAgICAiVGVtcGxhdGVQYXJhbXMiOlsKICAgICAgICAgICAgICAgICAgICAi6aG257qn6ZK755+z55So5oi35YiY5aSn6ZSkIiwKICAgICAgICAgICAgICAgICAgICAiMjQ2ODAiCiAgICAgICAgICAgICAgICBdLAogICAgICAgICAgICAgICAgIlBob25lIjoiMTg1WFhYWDA1MDciLAogICAgICAgICAgICAgICAgIlVzZXJJZCI6InlvdSBtYW4gYyBkZWZpbmUgdGhlIGNvbnRlbnQgYnkgeXJzZWxmIgogICAgICAgICAgICB9LAogICAgICAgICAgICB7CiAgICAgICAgICAgICAgICAiVGVtcGxhdGVQYXJhbXMiOlsKICAgICAgICAgICAgICAgICAgICAi5byA5b+D5p6c5oyW5Zyf5py6IiwKICAgICAgICAgICAgICAgICAgICAiMTM1NzkiCiAgICAgICAgICAgICAgICBdLAogICAgICAgICAgICAgICAgIlBob25lIjoiMTg1WFhYWDA2MDgiLAogICAgICAgICAgICAgICAgIkV4dGVuZENvZGUiOiIxMjMiLAogICAgICAgICAgICAgICAgIlVzZXJJZCI6ImNhdGNoIHRoZSBiaWcgZmlzaCIKICAgICAgICAgICAgfQogICAgICAgIF0KICAgIH0KXQ==

```

### 响应示例
    
```json
{
  "Action": "SendBatchUSMSMessageResponse",
  "FailContent": [
    {
      "FailureDetails": "phone in the black list",
      "SigContent": "UCloud",
      "Target": [
        {
          "ExtendCode": "123",
          "Phone": "185XXXX0608",
          "TemplateParams": [
            "开心果挖土机",
            "13579"
          ],
          "UserId": "catch the big fish"
        }
      ],
      "TemplateId": "UTA20212831C85C"
    }
  ],
  "Message": "submit success",
  "ReqUuid": "abcd-dadd-dafs-dadfa-dafdsa",
  "RetCode": 0,
  "SessionNo": "abcd-dadd-dafs-dadfa-dafdsa",
  "SuccessCount": 2
}
```





