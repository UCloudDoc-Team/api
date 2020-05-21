# 创建加速实例转发器 - CreateUGAForwarder

## 简介

创建加速实例转发器，支持HTTPS接入HTTPS回源、HTTPS接入HTTP回源、HTTP接入HTTP回源、TCP接入TCP回源、UDP接入UDP回源、 支持WSS接入WSS回源、WSS接入WS回源、WS接入WS回源

?> 目前UGA同时支持4层和7层接入端口 使用相同的加速域名接入。因此TCP协议接入端口与HTTP(s)类协议接入端口不能相同；如果需要从TCP加速转为HTTP加速，请先使用DeleteUGAForwarder接口删除已经存在的TCP端口加速再使用CreateUGAForwarder增加七层加速端口；修改回源端口也需要删除现有的端口加速再添加新的




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUGAForwarder)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUGAForwarder`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **UGAId** | string | 加速配置实例ID |**Yes**|
| **HTTPHTTP.N** | int | HTTP接入HTTP回源转发，接入端口。禁用65123端口 |No|
| **HTTPHTTPRS.N** | int | HTTP接入HTTP回源转发，源站监听端口 |No|
| **HTTPSHTTP.N** | int | HTTPS接入HTTP回源转发，接入端口。禁用65123端口 |No|
| **HTTPSHTTPRS.N** | int | HTTPS接入HTTP回源转发，回源端口 |No|
| **HTTPSHTTPS.N** | int | HTTPS接入HTTPS回源转发，接入端口。禁用65123端口 |No|
| **HTTPSHTTPSRS.N** | int | HTTPS接入HTTPS回源转发，源站监听端口 |No|
| **TCP.N** | int | TCP接入端口 |No|
| **TCPRS.N** | int | TCP回源端口 |No|
| **UDP.N** | int | UDP接入端口 |No|
| **UDPRS.N** | int | UDP回源端口 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUGAForwarder
&ProjectId=org-xxxx
&UGAId=uga-xxxx
&HTTPHTTP.n=80
&HTTPHTTPRS.n=80
&HTTPSHTTP.n=443
&HTTPSHTTPRS.n=80
&TCP.n=22
&TCPRS.n=22
```

### 响应示例
    
```json
{
  "Action": "CreateUGAForwarderResponse",
  "Message": "",
  "RetCode": 0
}
```





