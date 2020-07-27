# 获取命名查询列表 - ListNamedQueries

## 简介

获取用户保存的SQL查询列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListNamedQueries)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListNamedQueries`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID，不填则为默认项目 |No|
| **Limit** | int | 个数（最大1000，默认100） |No|
| **Offset** | int | 偏移（默认0） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Request** | string | API请求ID |No|
| **TotalCount** | int | 保存的SQL查询总数 |No|
| **NamedQueries** | array[[*NamedQuery*](#NamedQuery)] | 保存的SQL查询集合 |No|

#### 数据模型


#### NamedQuery

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NamedQueryId** | int | 已保存查询ID |**Yes**|
| **QueryName** | string | 查询名称 |No|
| **QueryDescription** | string | 查询描述 |No|
| **QueryString** | string | 查询SQL语句 |No|
| **CreateTime** | int | 查询创建时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListNamedQueries
&Region=cn-xxxx
&ProjectId=org-33511
&Limit=20
&Offset=0

```

### 响应示例
    
```json
{
  "Action": "ListNamedQueriesResponse",
  "NamedQueries": [
    {
      "CreateTime": "2018-08-14T12:55:54.000+0000",
      "QueryDescription": "yyyyyyyyyy",
      "QueryId": 1,
      "QueryName": "named_sql",
      "QueryString": "SELECT * FROM xxxxxx;"
    }
  ],
  "Request": "2a7a6712-f837-4cb9-a33c-b81f37917ef3",
  "RetCode": 0,
  "TotalCount": 1
}
```





