# 查询语言模型信息 - QueryMVLLMList

## 简介

查询可用的语言模型列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryMVLLMList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LLMID** | string | 语言模型ID (缺省则返回所有模型列表) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LLMInfoList** | array[[*LLMInfo*](#LLMInfo)] | 语言模型列表 |**Yes**|
| **Msg** | string | 状态码描述 |No|

#### 数据模型


#### LLMInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LLMID** | string | 模型ID |No|
| **LLMName** | string | 模型名称 |No|
| **LLMType** | int | 模型类型 |No|
| **LLMDes** | string | 模型描述 |No|
| **LLMPrice** | float | 模型token单价 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryMVLLMList
&LLMID=TTpidSNH
```

### 响应示例
    
```json
{
  "Action": "QueryMVLLMListResponse",
  "LLMInfoList": [
    "LNiHiScq"
  ],
  "Msg": "iImCxPqT",
  "RetCode": 0
}
```





