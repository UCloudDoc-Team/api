# 获取DNS或FILE验证信息 - GetDVAuthInfo

## 简介

获取DNS或FILE验证信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetDVAuthInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateID** | int | 购买的证书编号 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AuthMethod** | string | 验证方式DNS\|FILE |**Yes**|
| **Auths** | array[[*AuthSet*](#AuthSet)] | 验证的内容 |**Yes**|

#### 数据模型


#### AuthSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AuthKey** | string | DNS对应的CNAME的key，FILE对应的文件名称 |**Yes**|
| **AuthValue** | string | DNS对应CNAME的value，FILE对应的文件内容 |**Yes**|
| **Domain** | string | 域名 |**Yes**|
| **AuthPath** | string | FILE对应的文件路径 |**Yes**|
| **AuthRecord** | string | dns对应的记录值 |**Yes**|
| **AuthType** | string |  |**Yes**|
| **AuthFile** | string |  |**Yes**|
| **AuthMethod** | string |  |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetDVAuthInfo
&CertificateID=1
```

### 响应示例
    
```json
{
  "Action": "GetDVAuthInfoResponse",
  "AuthMethod": "DNS",
  "Auths": [
    {
      "authKey": "s5iljpx7j6dvmup5i4nyxwb4z3rfvnwj.bestenover.com",
      "authValue": "s20170106185910.bestenover.com",
      "domain": "www.bestenover.com"
    }
  ],
  "RetCode": 0
}
```





