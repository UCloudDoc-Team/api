# 修改角色 - ModifyCharacter

## 简介

修改角色






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ModifyCharacter)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyCharacter`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CharacterId** | string | 角色ID |**Yes**|
| **CharacterName** | string | 新角色名称 |No|
| **CharacterDescription** | string | 角色描述 |No|
| **Add.N** | string | 角色权限(增) |No|
| **Del.N** | string | 角色权限(删) |No|
| **Mod.N** | string | 角色权限(改) |No|
| **Get.N** | string | 角色权限(查) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyCharacter
&CharacterId=qehEhJUw
&CharacterName=PmyyaiHK
&CharacterDescription=pGpdGkyB
&Add.n=llPVKzpb
&Del.n=ijIaeoEI
&Mod.n=CYtcuRJO
&Get.n=nGnUpKat
```

### 响应示例
    
```json
{
  "Action": "ModifyCharacterResponse",
  "RetCode": 0
}
```





