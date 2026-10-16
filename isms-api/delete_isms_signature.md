# 删除视频短信签名 - DeleteISMSSignature

## 简介

调用接口DeleteISMSSignature删除视频短信签名



!> 1.不支持删除正在审核中的短信签名；2.短信签名删除后不可恢复，请谨慎操作。





## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DeleteISMSSignature`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID，不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **SigIds.N** | string | 签名ID，支持以数组的方式，举例，以SigIds.0、SigIds.1...SigIds.N方式传入    |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DeleteISMSSignature
&ProjectId=wExXZRHx
&SigIds.N=xiCVYJAk
```

### 响应示例
    
```json
{
  "Action": "DeleteISMSSignatureResponse",
  "Message": "xUNeSDLK",
  "RetCode": 0
}
```





