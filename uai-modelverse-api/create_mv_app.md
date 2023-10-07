# 创建应用 - CreateMVApp

## 简介

提供参数创建应用






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateMVApp`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppName** | string | 应用名称 |**Yes**|
| **AppType** | int | 应用类型 |**Yes**|
| **LLMID** | string | 语言模型ID |**Yes**|
| **LLMTemperature** | int | 模型采样温度 ，(0，100) 开区间，不能等于 0 或 100，默认值95 |No|
| **LLMTopP** | int | 模型采样温度（核取样）， (0，100) 开区间，不能等于 0 或 100，默认值70 |No|
| **AppDes** | string | 应用描述 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | Code非0时，描述错误信息 |**Yes**|
| **AppInfo** | [*AppInfo*](#AppInfo) | 应用信息 |**Yes**|

#### 数据模型


#### AppInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppName** | string | 应用名称 |No|
| **AppID** | string | 应用ID |No|
| **AppType** | int | 应用类型 |No|
| **AppDes** | string | 应用描述 |No|
| **AppState** | int | 应用状态 |No|
| **LLMID** | string | 语言模型ID |No|
| **LLMTemperature** | int | 模型采样温度 |No|
| **LLMTopP** | int | 模型采样温度的另一种方法（核取样） |No|
| **CreateTime** | int | 应用创建时间 |No|
| **UpdateTime** | int | 应用更新时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateMVApp
&AppName=pRwgTpER
&AppType=6
&LLMID=BtTWclTl
&LLMTemperature=5
&LLMTopP=4
&AppDes=cIBGvFSV
```

### 响应示例
    
```json
{
  "Action": "CreateMVAppResponse",
  "AppInfo": {},
  "Msg": "MHZLcsLH",
  "RetCode": 0
}
```





