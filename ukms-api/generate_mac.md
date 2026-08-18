# 生成MAC - GenerateMac

## 简介

使用HMAC密钥管理服务（KMS）密钥和该密钥支持的MAC算法，为消息生成基于哈希的消息认证码（HMAC）。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GenerateMac)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GenerateMac`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **KeyId** | string | 密钥ID |**Yes**|
| **MacMessage** | string | 待哈希的消息。 |**Yes**|
| **MacAlgorithm** | string | 用于生成消息认证码的 MAC 算法。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Mac** | string | 针对指定消息生成的基于哈希的消息认证码 (HMAC)、HMAC KMS 密钥和 MAC 算法。 |No|
| **MacAlgorithm** | string | 用于生成 HMAC 的 MAC 算法。 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GenerateMac
&Region=cn-zj
&ProjectId=bDwrrfPB
&KeyId=PYKoiAJJ
&MacMessage=NeCdOpew
&MacAlgorithm=pIKmIPDy
```

### 响应示例
    
```json
{
  "Action": "GenerateMacResponse",
  "RetCode": 0
}
```





