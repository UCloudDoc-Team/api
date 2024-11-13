# 添加跨域规则 - AddCORSRule

## 简介

添加跨域规则






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddCORSRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddCORSRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BucketName** | string | Bucket名称 |**Yes**|
| **AllowedOrigin** | string | 指定允许的跨域请求的来源，使用通配符(*)表示允许所有来源的跨域请求（多个Origin用‘,’分隔） |**Yes**|
| **AllowedMethod** | string | 指定允许的跨域请求方法。支持的方法名有：GET、PUT、POST、DELETE、HEAD、OPTIONS（多个Method用‘,’分隔） |**Yes**|
| **AllowedHeader** | string | 指定允许的跨域请求头（多个Header用‘,’分隔） |No|
| **ExposeHeader** | string | 指定允许用户从应用程序中访问的响应头（多个ExposeHeader用‘,’分隔） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CORSId** | string | 增加一条跨域规则的cors_id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddCORSRule
&BucketName=zovBREtA
&Origin=JHadvfLW
&Method=dtinCAUg
&MaxAge=2
&Header=WGZPTauj
&ExposeHeader=gOGmfrie
&ProjectId=ZdxNuOEg
```

### 响应示例
    
```json
{
  "Action": "AddCORSRuleResponse",
  "CORSId": "gdoTXICF",
  "RetCode": 0
}
```





