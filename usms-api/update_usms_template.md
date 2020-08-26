# 修改短信模板 - UpdateUSMSTemplate

## 简介

调用接口UpdateUSMSTemplate修改未通过审核的短信模板，并重新提交审核

?> 修改消息模板。用于修改现有模板，提交成功后，若修改了模板内容，模板状态等会重置到初创状态；若只修改模板名称，则不会重置




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateUSMSTemplate)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateUSMSTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **TemplateId** | string | 短信模板ID |**Yes**|
| **Template** | string | 新的模板内容。模板名称和模板内容必须提供一个，否则会报错。小于等于600个字 |**Yes**|
| **TemplateName** | string | 新的模板名称。小于等于32个字，每个中文、英文、数组、符合都计为一个字 |No|
| **Remark** | string | 短信模板申请原因说明，字数不超过128，每个中文、符号、英文、数字等都计为1个字。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateUSMSTemplate
&ProjectId=org-bxxxxy
&TemplateId=UTA1908XXXX8B3F
&Template=alertXXXXXXXXXXXXXXXXXXXXXXXX
&TemplateName=ucloud-alert
&Remark=XXXXXXXXXXXXXXX
&UnsubscribeInfo=sUGREgjQ
```

### 响应示例
    
```json
{
  "Action": "UpdateUSMSTemplateResponse",
  "Message": "",
  "RetCode": 0
}
```





