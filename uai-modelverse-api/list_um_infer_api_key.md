# 列表查询APIKey - ListUMInferAPIKey

## 简介

列表查询apikey






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUMInferAPIKey)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUMInferAPIKey`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list)   |**Yes**|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|
| **ModelverseDisabled** | int | 是否modelverse可用 0: 启用 1: 禁用 |No|
| **SandBoxDisabled** | int | 是否沙盒可用 0: 启用 1: 禁用(astraflow 沙盒控制未上线，暂时无效) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*APIKey*](#APIKey)] | apikey |**Yes**|

#### 数据模型


#### APIKey

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IPWhitelist** | string | ip白名单，换行分割的多组ip。支持IPv4和网段,输入后回车生效,最多100个, 示例: ﻿ 192.168.1.1 192.168.1.10-192.168.1.100 192.168.1.10/24 |**Yes**|
| **KeyId** | string | 资源ID |No|
| **Name** | string | 名称 |No|
| **ChannelId** | int | 渠道id |No|
| **TopOrganizationId** | int | 公司id |No|
| **OrganizationId** | int | 项目id |No|
| **Status** | int | 状态，1 正常 |No|
| **CreateTime** | int | 创建时间 |No|
| **Key** | string | 密钥值 |No|
| **ExpireTime** | int | 过期时间的unix时间戳，-1 用不过期 |No|
| **ModelverseDisabled** | int | 是否modelverse可用 0: 启用 1: 禁用 |No|
| **SandBoxDisabled** | int | 是否沙盒可用 0: 启用 1: 禁用(astraflow 沙盒控制未上线，暂时无效) |No|
| **DailyLimitAmount** | string | 日限额，单位随用户所在渠道。126渠道单位为美元 |No|
| **MonthlyLimitAmount** | string | 月限额，单位随用户所在渠道。126渠道单位为美元 |No|
| **GrantAllModels** | boolean | 全部模型访问开关，开启不受 GrantedModels 参数控制，关闭只能访问 GrantedModels 中添加模型 |No|
| **GrantedModels** | array[string] | 授权的模型，英文逗号分隔，all表示所有模型都有权限 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUMInferAPIKey
&Offset=7
&Limit=5
&ProjectId=BwpkilUS
&ModelverseDisabled=5
&SandBoxDisabled=5
```

### 响应示例
    
```json
{
  "Action": "ListUMInferAPIKeyResponse",
  "Data": {},
  "RetCode": 0
}
```





