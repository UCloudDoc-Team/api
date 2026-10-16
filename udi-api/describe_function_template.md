# 获取功能模板 - DescribeFunctionTemplate

## 简介

获取功能模板






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeFunctionTemplate)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeFunctionTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Type** | string | 功能模板类型：预设（preset）自定义（custom），为空则获取两种类型 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Templates** | array[[*FunctionTemplate*](#FunctionTemplate)] | 功能模板 |No|

#### 数据模型


#### FunctionTemplate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Name** | string |  |No|
| **FunctionName** | string |  |No|
| **Id** | string |  |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeFunctionTemplate
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=OcpbgJgf
&Type=huvyDVNb
```

### 响应示例
    
```json
{
  "Action": "DescribeFunctionTemplateResponse",
  "ErrMsg": "xhWomjLo",
  "RetCode": 0,
  "Templates": [
    {
      "FunctionName": "DXmQKnGJ",
      "Id": "KAWzTrfg",
      "Name": "WAnanWIR"
    }
  ]
}
```





