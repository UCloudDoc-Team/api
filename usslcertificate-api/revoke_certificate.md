# 申请吊销证书 - RevokeCertificate

## 简介

申请吊销证书









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `RevokeCertificate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateID** | int | 购买的证书编号 |**Yes**|
| **Reason** | string | 吊销证书的原因 |**Yes**|
| **RevokeLetter** | string | OV、EV证书吊销需要提供此参数 文件base64编码 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=RevokeCertificate
&RevokeLetter=GSIipMNU
&CertificateID=1
&Reason=dismiss
```

### 响应示例
    
```json
{
  "Action": "RevokeCertificateResponse",
  "RetCode": 0
}
```





