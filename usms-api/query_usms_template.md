# 查询短信模板申请状态 - QueryUSMSTemplate

## 简介

调用接口QueryUSMSTemplate查询短信模板申请状态






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=QueryUSMSTemplate)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryUSMSTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **TemplateId** | string | 模板ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*OutTemplate*](#OutTemplate) | 短信模板明细信息，各字段说明详见OutTemplate |No|

#### 数据模型


#### OutTemplate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TemplateId** | string | 短信模板ID |**Yes**|
| **Purpose** | int | 模板类型，选项：1-验证码类 2-通知类 3-会员推广类 |**Yes**|
| **TemplateName** | string | 短信模板名称 |**Yes**|
| **Template** | string | 短信模板内容 |**Yes**|
| **UnsubscribeInfo** | string | 退订信息；一般填写方式“回T退订”，当purpose为3（也即会员推广类）时，为必填项 |**Yes**|
| **Status** | int | 短信模板状态；状态说明：0-待审核，1-审核中，2-审核通过，3-审核未通过，4-被禁用 |**Yes**|
| **Remark** | string | 模板说明 |**Yes**|
| **ErrDesc** | string | 审核失败原因 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryUSMSTemplate
&ProjectId=pro-xxxxx
&TemplateId=UTA190715D9108C
```

### 响应示例
    
```json
{
  "Action": "QueryUSMSTemplateResponse",
  "Data": {
    "CreateTime": 1566783067,
    "ErrDesc": "",
    "Status": 2,
    "Template": "您的验证码为{1}，请在{2}分钟内使用，勿透露给他人。",
    "TemplateId": "UTA190715D9108C",
    "TemplateName": "验证码模板01"
  },
  "Message": "",
  "RetCode": 0
}
```





