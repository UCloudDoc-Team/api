# 创建用户密钥 - CreateAccessKey

## 简介

创建用户密钥






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateAccessKey)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateAccessKey`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UserName** | string | 用户名 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AccessKey** | [*AccessKey*](#AccessKey) | 密钥实例 |No|

#### 数据模型


#### AccessKey

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AccessKeyID** | string | 用户公钥 |No|
| **UserId** | int | 用户ID |No|
| **AccessKeySecret** | string | 用户私钥 |No|
| **Description** | string | 密钥备注 |No|
| **Status** | string | 密钥状态 |No|
| **CreatedAt** | int | 密钥创建时间 |No|
| **ExpiredAt** | int | 密钥过期时间 |No|
| **UpdatedAt** | int | 密钥更新时间 |No|
| **DeletedAt** | int | 密钥删除时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateAccessKey
&UserName=XZENszQt
```

### 响应示例
    
```json
{
  "AccessKey": {},
  "Action": "CreateAccessKeyResponse",
  "RetCode": 0
}
```





