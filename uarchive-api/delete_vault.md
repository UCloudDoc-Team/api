# 删除Vault - DeleteVault

## 简介

删除Vault

?> 特别说明:<br />VaultName参数必须符合Vault名称规范,规范如下: (1) 长度在3\~63字节之间； (2) 可以由多个标签组成，各个标签用 . 间隔，每个标签只能包含小字母、数字、连接符（短横线），并且标签的开头和结尾的字符只能是小写字母或数字； (3) 不可以是IP地址。




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DeleteVault)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DeleteVault`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不选择为默认项目，子帐号必选 |No|
| **VaultName** | string | 待删除Vault的名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **VaultName** | string | 已创建Vault的名称 |No|
| **VaultId** | string | 已创建Vault的ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DeleteVault
&VaultName=blue
&ProjectId=WIpvovJc
```

### 响应示例
    
```json
{
  "Action": "DeleteVaultResponse",
  "Retcode": 0,
  "VaultId": "uarchive-xxx",
  "VaultName": "blue"
}
```





