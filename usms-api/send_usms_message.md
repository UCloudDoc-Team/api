# 发送短信 - SendUSMSMessage

## 简介

调用接口SendUSMSMessage发送短信

?> 支持在一次请求中向多个不同的手机号码发送相同内容的短信；

!> 在一次请求中，最多可以向1000个手机号码发送相同内容的短信；


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=SendUSMSMessage)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SendUSMSMessage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **PhoneNumbers.N** | string | 电话号码数组，电话号码格式为(60)1xxxxxxxx，()中为国际长途区号(如中国为86或0086，两种格式都支持)，后面为电话号码.若不传入国际区号，如1851623xxxx，则默认为国内手机号 |**Yes**|
| **SigContent** | string | 短信签名内容，请到[USMS控制台](https://console.ucloud.cn/usms)的签名管理页面查看；使用的短信签名必须是已申请并且通过审核； |**Yes**|
| **TemplateId** | string | 模板ID（也即短信模板申请时的工单ID），请到[USMS控制台](https://console.ucloud.cn/usms)的模板管理页面查看；使用的短信模板必须是已申请并通过审核； |**Yes**|
| **TemplateParams.N** | string | 模板可变参数，以数组的方式填写，举例，TempalteParams.0，TempalteParams.1，... 若模板中无可变参数，则该项可不填写；若模板中有可变参数，则该项为必填项，参数个数需与变量个数保持一致，否则无法发送； |No|
| **ExtendCode** | string | 短信扩展码，格式为阿拉伯数字串，默认不开通，如需开通请联系 UCloud技术支持 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SessionNo** | string | 本次提交发送的短信的唯一ID，可根据该值查询本次发送的短信列表 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SendUSMSMessage
&ProjectId=org-XXXXqi
&PhoneNumbers.0=185XXXX9057
&TemplateParams.0=123456
&SigContent=UCloud
&TemplateId=UTA19XXXX2D5BEC
&PublicKey=vsRhB0Qzo9elXXXXXkw8o/vmss8Tb0vxi74A=
```

### 响应示例
    
```json
{
  "Action": "SendUSMSMessageResponse",
  "Message": "提交发送成功",
  "RetCode": 0,
  "SessionNo": "5a3XXXXXXb-7XXXX2-4XXX"
}
```





