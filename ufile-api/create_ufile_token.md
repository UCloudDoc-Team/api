# 创建US3令牌 - CreateUFileToken

## 简介

创建US3令牌






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUFileToken)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUFileToken`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **TokenName** | string | 令牌名称 |**Yes**|
| **AllowedOps.N** | string | 令牌允许执行的操作<br />[ TOKEN_ALLOW_NONE 没有权限, TOKEN_ALLOW_READ 下载权限 , TOKEN_ALLOW_WRITE 上传权限 , TOKEN_ALLOW_DELETE 删除权限 , TOKEN_ALLOW_LIST 列表权限, TOKEN_ALLOW_IOP 图片处理权限, TOKEN_DENY_UPDATE 禁止覆盖权限]。默认TOKEN_ALLOW_NONE |No|
| **AllowedPrefixes.N** | string | 令牌允许操作的key前缀，默认*表示全部 |No|
| **AllowedBuckets.N** | string | 令牌允许操作的bucket，默认*表示全部 |No|
| **ExpireTime** | int | Unix 时间戳，精确到秒，为令牌过期时间点。默认过期时间为一天（即当前Unix时间戳+86400）；注意：过期时间不能超过 4102416000 |No|
| **BlackIPList.N** | string | 令牌黑名单，支持ipv4，ipv6格式。 |No|
| **WhiteIPList.N** | string | 令牌白名单，支持ipv4，ipv6格式。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TokenId** | string | 令牌唯一ID |No|
| **UFileTokenSet** | [*UFileTokenSet*](#UFileTokenSet) | 创建令牌的详细信息 |No|

#### 数据模型


#### UFileTokenSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 所属地区 |**Yes**|
| **TokenId** | string | 令牌ID |**Yes**|
| **TokenName** | string | 令牌名称 |**Yes**|
| **PublicKey** | string | 令牌公钥 |**Yes**|
| **PrivateKey** | string | 令牌私钥 |**Yes**|
| **AllowedOps** | array[string] | 令牌允许执行的操作，[ TOKEN_ALLOW_NONE 没有权限, TOKEN_ALLOW_READ 下载权限, TOKEN_ALLOW_WRITE 上传权限, TOKEN_ALLOW_DELETE 删除权限, TOKEN_ALLOW_LIST 列表权限, TOKEN_ALLOW_IOP 图片处理权限] |**Yes**|
| **AllowedPrefixes** | array[string] | 令牌允许操作的key前缀 |**Yes**|
| **AllowedBuckets** | array[string] | 令牌允许操作的bucket |**Yes**|
| **ExpireTime** | int | 令牌的超时时间点 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **ModifyTime** | int | 修改时间 |**Yes**|
| **BlackIPList** | array[string] | 令牌黑名单 |No|
| **WhiteIPList** | array[string] | 令牌白名单 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUFileToken
&Region=ZidvwRDV
&ProjectId=ykZiYbvH
&TokenName=ZwctpTkP
&AllowedOps.n=yes
&AllowedPrefixes.n=BxWpXPuh
&AllowedBuckets.n=tPAdQHnf
&ExpireTime=3
&BlackIPList.n=WGGVYtQm
&WhiteIPList.n=kBRhXipR
```

### 响应示例
    
```json
{
  "Action": "CreateUFileTokenResponse",
  "RetCode": 0,
  "TokenId": "ygqCyolZ",
  "UFileTokenSet": {}
}
```





