# 删除加速实例转发器 - DeleteUGAForwarder

## 简介

删除加速实例转发器 按接入端口删除



!> 删除端口转发器会导致服务立刻失效 请谨慎操作。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DeleteUGAForwarder)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DeleteUGAForwarder`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **UGAId** | string | 加速配置实例ID |**Yes**|
| **HTTPHTTP.N** | int | HTTP接入HTTP回源，接入端口。禁用65123端口 |No|
| **HTTPSHTTP.N** | int | HTTPS接入HTTP回源， 接入端口。禁用65123端口 |No|
| **HTTPSHTTPS.N** | int | HTTPS接入HTTPS回源， 接入端口。禁用65123端口 |No|
| **TCP.N** | int | TCP接入端口 |No|
| **UDP.N** | int | UDP接入端口 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DeleteUGAForwarder
&ProjectId=org-xxxx
&UGAId=uga-xxxx
&HTTPHTTP.n=80
&HTTPSHTTP.n=443
&TCP.n=22
```

### 响应示例
    
```json
{
  "Action": "DeleteUGAForwarderResponse",
  "Message": "",
  "RetCode": 0
}
```





