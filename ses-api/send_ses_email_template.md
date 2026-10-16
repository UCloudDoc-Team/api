# 发送模版邮件 - SendSESEmailTemplate

## 简介

通过模版发送邮件，无需创建发送任务。支持自定义主题、摘要、预览文本、抄送/密送、附件和邮件头，单次最多 100 个收件人。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SendSESEmailTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **TemplateId** | string | 模版 ID，获取：https://console.ucloud.cn/ses/email-config?tab=template |**Yes**|
| **From** | string | 发件人邮箱 |**Yes**|
| **Subject** | string | 邮件主题 |**Yes**|
| **PreHeader** | string | 邮件预览文本 |No|
| **EmailContent.N.To** | string | 收件人，最多100条 |No|
| **EmailContent.N.Cc.N** | string | 抄送（抄送+密送总数量不能超过100） |No|
| **EmailContent.N.Bcc.N** | string | 密送（抄送+密送总数量不能超过100） |No|
| **EmailContent.N.TemplateVariableParams.N** | string | 模版变量，格式 variableName{##}variableValue （例：{"name{##}Tom", "code{##}1234"}） |No|
| **FromName** | string | 发件人名称，不传或为空时，自动回落到该发件人在控制台配置的别名（Alias） |No|
| **Attachments.N.Filename** | string | 附件文件名 |No|
| **Attachments.N.ContentType** | string | MIME 类型，如： application/pdf |No|
| **Attachments.N.Data** | string | 附件内容（Base64 编码），单次请求最多 10 个附件；总大小不超过 10MB |No|
| **Headers.N.Name** | string | 邮件头名称，最多 20 个且仅允许字母、数字和 -（正则 ^[A-Za-z0-9-]+$）。禁止使用保留名称：From/To/Cc/Bcc/Subject/Reply-To/Content-Type/Mime-Version，以及 X-SES- 前缀（均不区分大小写）。 |No|
| **Headers.N.Value** | string | 邮件头值 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SessionNo** | string | 本次发送任务的唯一标识 |**Yes**|
| **SuccessCount** | int | 发送成功数 |**Yes**|
| **FailContent** | array[[*FailedTargetEmail*](#FailedTargetEmail)] | 发送失败的收件人列表 |**Yes**|

#### 数据模型


#### FailedTargetEmail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **To** | string | 收件人 |No|
| **EmailAddress** | string | 收件邮箱 |No|
| **Cc** | array[string] | 抄送 |No|
| **Bcc** | array[string] | 密送 |No|
| **TemplateVariableParams** | array[string] | 模版变量,variableName{##}variableValue 格式；仅使用模版发送（SendSESEmailTemplate）时返回，未使用模版发送（SendSESEmail）时不返回该字段 |No|
| **FailureReason** | string | 失败原因 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SendSESEmailTemplate
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=jfBEnVOE
&TemplateId=swzOepQk
&From=JvhEchJX
&SendEmail=OMfHgOkG
&Subject=BrGzkTZF
&AbstractContent=pBytsvBC
&PreHeader=vTwUmIZn
&EmailContent.N.To=RqETNYdB
&EmailContent.N.EmailAddress=qzcuGLGo
&EmailContent.N.Cc.N=zSYENiBo
&EmailContent.N.Bcc.N=vfvLqcQL
&EmailContent.N.TemplateVariableParams.N=HuNLQCQk
&FromName=IDyqZpry
&Cc.N=OYpBmhOW
&Bcc.N=ozxlubmR
&Attachments.N.Filename=tFvFUKpw
&Attachments.N.ContentType=ZinulSkB
&Attachments.N.Data=tVfgmtfD
&Headers.N.Name=pCkUIqyp
&Headers.N.Value=RxJHxbxW
```

### 响应示例
    
```json
{
  "Action": "SendSESEmailTemplateResponse",
  "FailContent": [
    {
      "Bcc": [
        "MJiWLqeQ"
      ],
      "Cc": [
        "rUKnHtyC"
      ],
      "EmailAddress": "aZXDpwoY",
      "FailureReason": "kxVnCpQZ",
      "TemplateVariableParams": [
        "qWvWfRfr"
      ],
      "To": "peEaUNkb"
    }
  ],
  "RetCode": 0,
  "SessionNo": "TCFvrDqb",
  "SuccessCount": 5
}
```





