# 获取PG实例参数信息 - GetUPgSQLInstanceParam

## 简介

获取实例参数信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUPgSQLInstanceParam)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUPgSQLInstanceParam`                        | **Yes** |
| **PublicKey**  | string  | AccessKey ID，在 [控制台](https://console.ucloud.cn/uaccount/api_manage) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **InstanceID** | string | 实例ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*Param*](#Param)] | 参数的键值对信息 |**Yes**|

#### 数据模型


#### Param

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Key** | string | 参数Key |No|
| **Value** | string | 参数值 |No|
| **ValueType** | int | 值类型 |No|
| **AllowedVal** | string | 允许的值 |No|
| **ApplyType** | int | 允许类型 |No|
| **Modifiable** | boolean | 是否可以修改 |No|
| **FormatType** | int | 参数格式类型 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUPgSQLInstanceParam
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=lEDEBrYR
&InstanceID=abHfDSym
```

### 响应示例
    
```json
{
  "Action": "GetUPgSQLInstanceParamResponse",
  "Data": [
    {
      "AllowVal": "tEzqXREZ",
      "ApplyType": 4,
      "FormatType": 2,
      "Key": "IYtqXSlR",
      "Modifiable": true,
      "Value": "YlCbndyj",
      "ValueType": 5
    }
  ],
  "RetCode": 0
}
```





