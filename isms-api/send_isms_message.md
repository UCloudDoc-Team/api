# 发送视频短信 - SendISMSMessage

## 简介

发送视频短信









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SendISMSMessage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **TemplateId** | string | 视频短信模板Id |**Yes**|
| **PhoneSet.N** | string | 手机号码列表。暂时只支持中国大陆号码。若号码中带区号，需要将区号使用小括号包含，放在号码前面。如: (86)1851623xxxx |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ReqUuid** | string | 本次请求uuid |**Yes**|
| **TaskId** | string | 本次调用TaskId，使用该字段查询回执信息 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SendISMSMessage
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=EkNSajhM
&TemplateId=pAZelVFJ
&PhoneSet.N=imMxkYUz
&TemplateParameters=gYJDeuXu
&TemplateParameters=uxmiQtzz
```

### 响应示例
    
```json
{
  "Action": "SendISMSMessageResponse",
  "Message": "lCkANCFf",
  "ReqUuid": "YBfQfZDR",
  "RetCode": 0,
  "TaskId": "EOtMIgwV"
}
```





