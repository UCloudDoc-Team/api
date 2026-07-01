# 查询角色信息列表 - ListRoles

## 简介

查询角色信息列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListRoles)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListRoles`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Offset** | string | 数据查询偏移量 |No|
| **Limit** | string | 数据查询数量 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 数据返回条数，无数据时返回 0 |**Yes**|
| **Roles** | array[[*ListRoles*](#ListRoles)] | 角色信息列表 |No|

#### 数据模型


#### ListRoles

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RoleName** | string | 角色名称 |No|
| **RoleURN** | string | 角色URN |No|
| **IsEditable** | boolean | 是否可编辑（true：可编辑，false：不可编辑） |No|
| **Description** | string | 描述信息 |No|
| **CreatedAt** | int | 角色创建时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListRoles
&Offset=fUEEtYSu
&Limit=AzxhQTCE
```

### 响应示例
    
```json
{
  "Action": "ListRolesResponse",
  "RetCode": 0,
  "Roles": [
    {
      "CreatedAt": 7,
      "Description": "ouanuUaU",
      "IsEditable": true,
      "RoleName": "CTCgSmsG",
      "RoleURN": "qacnVzYs"
    }
  ],
  "TotalCount": 9
}
```





