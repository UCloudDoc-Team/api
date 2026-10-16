# 批量创建手机号黑名单 - BatchCreateUSMSBlacklistPhone

## 简介

批量创建手机号黑名单






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=BatchCreateUSMSBlacklistPhone)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BatchCreateUSMSBlacklistPhone`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **IsGlobal** | boolean | 是否全项目生效 |**Yes**|
| **BlackList** | string | 手机号黑名单列表,该参数是json数组的base64编码结果,单次不超过1000条;子项参数说明:<br />     {<br />      "Phone": "13900000001", 手机号 类型:string<br />      "Purpose": 2,短信类型 类型int :0-不过滤 1-验证码 2-通知 3-营销<br />      "Remark": "测试数据001" 备注 类型 string(最大256字符)<br />    }<br /><br />           Remark: 备注(最大256字符)示例：<br />示例:发送内容json数组(base64编码前):<br />[<br />     {<br />      "Phone": "13900000001",<br />      "Purpose": 2,<br />      "Remark": "测试数据001" <br />    }<br />]<br />示例:发送内容json数组(base64编码后):<br />Ww0KICAgICB7DQogICAgICAiUGhvbmUiOiAiMTM5MDAwMDAwMDEiLA0KICAgICAgIlB1cnBvc2UiOiAyLA0KICAgICAgIlJlbWFyayI6ICLmtYvor5XmlbDmja4wMDEiIA0KICAgIH0NCl0=<br />其他:<br />    支持的手机号格式<br />        1. 带括号的手机号，括号里面是国家码 (a)xxxxx<br />        2. 不带括号的手机号 axxxxxx<br />        3. 带加号的手机号 +axxxxx |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ReqUuid** | string | 本次请求Uuid |**Yes**|
| **SuccessList** | array[string] | 创建成功的手机号列表 示例["13900000001","13900000002] |**Yes**|
| **FailedList** | array[string] | 创建失败的手机号列表 示例["13900000003","13900000004] |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BatchCreateUSMSBlacklistPhone
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=tHdAlChQ
&IsGlobal=true
&BlackList=Ww0KICAgICB7DQogICAgICAiUGhvbmUiOiAiMTM5MDAwMDAwMDEiLA0KICAgICAgIlB1cnBvc2UiOiAyLA0KICAgICAgIlJlbWFyayI6ICLmtYvor5XmlbDmja4wMDEiIA0KICAgIH0NCl0=
```

### 响应示例
    
```json
{
  "Action": "BatchCreateUSMSBlacklistPhoneResponse",
  "FailedList": [
    "13900000003",
    "13900000004"
  ],
  "Message": "Success",
  "ReqUuid": "ezKmluyR",
  "RetCode": 0,
  "SuccessList": [
    "13900000001",
    "13900000002"
  ]
}
```





