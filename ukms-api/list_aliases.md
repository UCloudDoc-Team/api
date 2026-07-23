# 获取别名列表 - ListAliases

## 简介

获取 UKMS 实例下的别名列表。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListAliases)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListAliases`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。参见地域和可用区列表。 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子账号必须填写。 |No|
| **ResourceId** | string | UKMS 实例资源 ID。 |**Yes**|
| **KeyId** | string | 可选：筛选指定密钥资源长 ID 的别名。 |No|
| **Offset** | int | 列表起始位置偏移量。 |No|
| **Limit** | int | 返回数据长度。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 别名总数。 |**Yes**|
| **Aliases** | array[[*AliasInfo*](#AliasInfo)] | 别名列表，每项为 AliasInfo。 |**Yes**|

#### 数据模型


#### AliasInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AliasName** | string | 别名，含 alias/ 前缀。 |**Yes**|
| **TargetKeyId** | string | 别名指向的密钥资源长 ID。 |**Yes**|
| **CreationDate** | int | 创建时间，Unix 时间戳。 |**Yes**|
| **LastUpdatedDate** | int | 最后更新时间，Unix 时间戳。 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListAliases
&Region=cn-zj
&ProjectId=HSPXGYLe
&Offset=3
&Limit=ZGdGcZeh
```

### 响应示例
    
```json
{
  "Action": "ListAliasesResponse",
  "RetCode": 0
}
```





