# 列出引用权限策略的实体 - ListEntitiesForPolicy

## 简介

列出引用权限策略的实体






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListEntitiesForPolicy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListEntitiesForPolicy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PolicyURN** | string | 策略URN |**Yes**|
| **Limit** | string | 需要查询的用户组数量 |No|
| **Offset** | string | 从第几条数据开始查询 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Entities** | array[[*Entity*](#Entity)] | 引用实体信息 |**Yes**|
| **TotalCount** | int | 数据集合数量 |**Yes**|

#### 数据模型


#### Entity

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **EntityName** | string | 实体名称 |**Yes**|
| **EntityKind** | string | 实体类型（User:用户，Group） |**Yes**|
| **AttachedAt** | int | 引用时间 |**Yes**|
| **DisplayName** | string | 子账户展示名称 |**Yes**|
| **Scope** | string | 生效空间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListEntitiesForPolicy
&PolicyURN=pesJEtsc
&Limit=rUqYHefJ
&Offset=FlrpwkMW
```

### 响应示例
    
```json
{
  "Action": "ListEntitiesForPolicyResponse",
  "Entities": [
    {
      "AttachedAt": 2,
      "EntityKind": "ye's",
      "EntityName": "DzyHLbZM"
    }
  ],
  "Message": "woIAThQp",
  "RetCode": 0,
  "TotalCount": "wlIhaDZN"
}
```





