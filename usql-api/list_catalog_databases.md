# 获取数据库列表 - ListCatalogDatabases

## 简介

用户获取自己账号下的所有数据库名称列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListCatalogDatabases)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListCatalogDatabases`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID，不填则为默认项目 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Request** | string | 请求ID |No|
| **TotalCount** | int | 数据库总数 |No|
| **DatabaseNames** | array[string] | 数据库名称列表 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListCatalogDatabases
&Region=cn-bj
&ProjectId=RFQCWdDK
```

### 响应示例
    
```json
{
  "Action": "ListCatalogDatabasesResponse",
  "DatabaseNames": [
    "default"
  ],
  "Request": "44ba2fe7-34ea-4d65-9a35-5f068e9ed12b",
  "RetCode": 0,
  "TotalCount": 1
}
```





