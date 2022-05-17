# 发送语音消息 - SendUVMSMessage

## 简介

向指定号码拨打电话









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SendUVMSMessage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CalledNumber** | string | 被叫号码，采用 E.164 标准，格式为+[国家代码][用户号码]。<br />例如：+8613512345678， 其中前面有一个+号 ，86为国家码，13512345678为手机号 |**Yes**|
| **TemplateId** | string | 模板 ID，在控制台审核通过的模板 ID。 |**Yes**|
| **TemplateParams.N** | string | 模板可变参数，以数组的方式填写，举例，TemplateParams.0，TemplateParams.1，... 若模板中无可变参数，则该项可不填写；若模板中有可变参数，则该项为必填项，参数个数需与变量个数保持一致，否则无法发送； |No|
| **FromNumber** | string | 主叫号码，号码随机时不填。专属号码时传入已购买的号码，仅支持一个号码，在控制台查看已购买的号码。 |No|
| **UserId** | string | 自定义的业务标识ID，字符串（ 长度不能超过32 位），不支持 单引号、表情包符号等特殊字符 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ReqUuid** | string | 唯一请求 ID，每次请求都会返回。定位问题时需要提供该次请求的 ReqUuid。 |**Yes**|
| **SessionNo** | string | 本次提交发送语音的唯一ID，可根据该值查询本次发送详情 |No|
| **UserId** | string | 	<br />本次提交的自定义业务标识ID，仅当发送时传入有效的UserId，才返回该字段。 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SendUVMSMessage
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=JMliDugq
&CalledNumber=+8613512345678
&TemplateId=xxxxxxxxx
&TemplateParams.0=123456
&UserId=ucloud
&FromNumber=IIiUKXds
```

### 响应示例
    
```json
{
  "Action": "SendUVMSMessageResponse",
  "Message": "Send success",
  "ReqUuid": "278fab0f-f0dc-4de6-a308-77f07ea276b4",
  "RetCode": 0,
  "SessionNo": "17ad00c9-8186-4e5a-8f64-c50a2c84cf0a",
  "Test": "SdZdBQda",
  "UserId": "ucloud"
}
```





