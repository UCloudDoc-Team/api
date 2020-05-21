# 绑定PathX SSL证书 - BindPathXSSL

## 简介

绑定PathX SSL证书






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=BindPathXSSL)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `BindPathXSSL`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **SSLId** | string | 证书ID，如果没有指定证书ID也没有申请免费证书，HTTPS接入无法正常工作 |**Yes**|
| **UGAId** | string | UGA实例ID |**Yes**|
| **Port.N** | int | 绑定SSL证书的HTTPS端口。Port.0 Port.1对应多个Port。如果Port不存在则不会绑定 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=BindPathXSSL
&ProjectId=org-xxxxx
&SSLId=gssl-xxxx
&UGAId=uga-xxxxx
&Port.n=443
```

### 响应示例
    
```json
{
  "Action": "BindPathXSSLResponse",
  "RetCode": 0
}
```





