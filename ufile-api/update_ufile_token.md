# 更新令牌 - UpdateUFileToken

## 简介

更新令牌的操作权限，可操作key的前缀，可操作bucket和令牌超时时间点






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateUFileToken)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateUFileToken`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **TokenId** | string | 令牌ID |**Yes**|
| **TokenName** | string | 令牌名称 |No|
| **AllowedOps.N** | string | 令牌允许执行的操作，[ TOKEN_ALLOW_NONE , TOKEN_ALLOW_READ , TOKEN_ALLOW_WRITE , TOKEN_ALLOW_DELETE , TOKEN_ALLOW_LIST, TOKEN_ALLOW_IOP , TOKEN_ALLOW_DP ] |No|
| **AllowedPrefixes.N** | string | 令牌允许操作的key前缀 |No|
| **AllowedBuckets.N** | string | 令牌允许操作的bucket |No|
| **ExpireTime** | int | 令牌的超时时间点（时间戳）;注意：过期时间不能超过 4102416000 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateUFileToken
&ProjectId=org-xxx
&Region=cn-bj
&TokenId=679c7e5e-74b8-4048-b622-33dd4e8634db
&TokenName=testname
&AllowedOps.0=TOKEN_ALLOW_READ 
&AllowedOps.1=TOKEN_ALLOW_WRITE
&AllowedPrefixes.0=test/test
&AllowedPrefixes.1=test1/test1
&AllowedPrefixes.2=test2/test2
&AllowedBuckets.0=bucket0
&AllowedBuckets.1=bucket1
&ExpireTime=1520411979
```

### 响应示例
    
```json
{
  "Action": "UpdateUFileTokenResponse",
  "RetCode": 0
}
```





