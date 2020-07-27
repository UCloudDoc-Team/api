# 创建主密钥 - CreateKey

## 简介

创建用户管理数据密钥的主密钥 CMK（Customer Master Key）。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateKey)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateKey`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Description** | string | 主密钥的描述信息, 长度不能超过 8192 个字符 |No|
| **Alias** | string | 别名，可为空，不能以ucloud/(不区分大小写)开头的保留别名，限制长度36字符，相同项目下别名不能重复 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Status** | string | 操作结果,如 success: 成功；failure: 失败 |No|
| **KeyId** | string | CMK 的唯一标识符 |No|
| **Description** | string | CMK 的相关描述说明 |No|
| **Enabled** | boolean | 是否启用 |No|
| **CreatedTime** | int | 创建时间 |No|
| **LastModifiedTime** | int | 最后修改时间 |No|
| **RequestUuid** | string | 此次请求的唯一标识符 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateKey
&ProjectId=org-mjwvpk
&Description=description
&Alias=nyScYpru
```

### 响应示例
    
```json
{
  "Action": "CreateKeyResponse",
  "CreatedTime": 1545049380,
  "Description": "description",
  "Enabled": true,
  "KeyId": "ukms-xxxx",
  "LastModifiedTime": 1545049380,
  "RequestUuid": "91a4229e-3c9f-4a81-85ab-68c6a14f3f99",
  "RetCode": 0,
  "Status": "success"
}
```





