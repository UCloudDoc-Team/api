# 查询角色信息 - GetRole

## 简介

查询角色信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetRole)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetRole`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RoleName** | string | 角色名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Role** | [*GetRole*](#GetRole) | 角色信息 |No|

#### 数据模型


#### GetRole

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RoleName** | string | 角色名称 |No|
| **RoleURN** | string | 角色标识 |No|
| **Description** | string | 描述信息 |No|
| **RolePolicyDocument** | string | 角色信息策略文本 |No|
| **MaxSessionDuration** | int | 角色最大会话时间 |No|
| **CreatedAt** | int | 创建时间 |No|
| **UpdatedAt** | string | 更新时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetRole
&RoleName=rihKswfL
```

### 响应示例
    
```json
{
  "Action": "GetRoleResponse",
  "RetCode": 0,
  "Role": {}
}
```





