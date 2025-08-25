# 创建apikey - CreateUMInferAPIKey

## 简介

创建apikey






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUMInferAPIKey)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUMInferAPIKey`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list)   |**Yes**|
| **Name** | string | apikey名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*APIKey*](#APIKey) | apikey |No|

#### 数据模型


#### APIKey

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **KeyId** | string | 资源ID |No|
| **Name** | string | 名称 |No|
| **ChannelId** | int | 渠道id |No|
| **TopOrganizationId** | int | 公司id |No|
| **OrganizationId** | int | 项目id |No|
| **Status** | int | 状态，1 正常 |No|
| **CreateTime** | int | 创建时间 |No|
| **Key** | string | 密钥值 |No|
| **ExpireTime** | int | 过期时间的unix时间戳，-1 用不过期 |No|
| **GrantedModels** | string | 授权的模型，英文逗号分隔，all表示所有模型都有权限 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUMInferAPIKey
&Name=ZBipIhpf
&ProjectId=ljHegiFu
```

### 响应示例
    
```json
{
  "Action": "CreateUMInferAPIKeyResponse",
  "Data": "SaaAxTCi",
  "RetCode": 0
}
```





