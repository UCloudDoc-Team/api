# 设置对象存储防盗链 - SetUFileReferer

## 简介

设置对象存储防盗链






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=SetUFileReferer)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `SetUFileReferer`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BucketName** | string | 存储空间名称 |**Yes**|
| **RefererStatus** | string | 开启关闭referer防盗链;关闭防盗链会清空防盗链参数设置，开启防盗链必须指定 RefererType、Referers；开启：on， 关闭：off; |**Yes**|
| **RefererAllowNull** | boolean | RefererType为白名单时，RefererAllowNull为false代表不允许空referer访问，为true代表允许空referer访问;<br />此参数默认为 true;  |No|
| **RefererType** | int | 防盗链Referer类型，支持三种类型，<br />1代表设置黑名单、2代表设置白名单，<br />3代表同时设置黑白名单; （其中1和2是为了向前兼容，后续调用只应该传递类型3）<br />RefererStatus为"on"时此参数必填； |No|
| **Referers.N** | string | 防盗链Referer规则，支持正则表达式（不支持符号';')，该字段已弃用，请使用WhiteList.n或BlackList.n |No|
| **WhiteList.N** | string | 白名单列表中的一项 |No|
| **BlackList.N** | string | 黑名单列表中的一项 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=SetUFileReferer
&Region=cn-zj
&ProjectId=EhCcaLxv
&BucketName=XvqwhKrY
&RefererType=ZzOlNzdj
&Referers.n=iaEJuvtY
&NullReferer=MrViJqjQ
&RefererStatus=开启：on; 关闭：off;
&RefererStatus=开启：on; 关闭：off;
&WhiteList.n=ZTziAPAx
&BlackList.n=gRpnOElW
&WhiteList.n=jCEtMJTO
&BlackList.n=CuicHvDo
&WhiteList.n=dQxkpotm
&BlackList.n=DhqOJukG
```

### 响应示例
    
```json
{
  "Action": "SetUFileRefererResponse",
  "RetCode": 0
}
```





