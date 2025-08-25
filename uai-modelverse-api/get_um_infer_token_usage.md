# 获取token使用量 - GetUMInferTokenUsage

## 简介

获取某个key下的某个模型的token使用量






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUMInferTokenUsage)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUMInferTokenUsage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list)   |**Yes**|
| **KeyId** | string | apikey的id |**Yes**|
| **Model** | string | 模型名称 |**Yes**|
| **StartTime** | int | 开始时间戳 |**Yes**|
| **EndTime** | int | 结束时间戳 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*TokenUsage*](#TokenUsage) | token使用详情 |**Yes**|

#### 数据模型


#### TokenUsage

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Total** | int | 总token量 |No|
| **InTotal** | int | 输出总token |No|
| **OutTotal** | int | 输出总token |No|
| **ImageGenerationNum** | int | 生图总张数 |No|
| **RequestTotal** | int | 请求总次数 |No|
| **Usages** | array[[*TokenUsageTimestamp*](#TokenUsageTimestamp)] | 每个时间戳的token使用量 |No|

#### TokenUsageTimestamp

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 类型，in输入 out输出 total总  request_count 请求次数 image_generation 生图张数 |No|
| **Count** | int | 数量 |No|
| **Timestamp** | int | unix时间戳 |No|
| **Model** | string | 模型名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUMInferTokenUsage
&KeyId=MBMtLxzV
&Model=RVLhTXwV
&StartTime=9
&EndTime=2
&ProjectId=pPuXjEjZ
&ProjectId=YyoGQFzG
```

### 响应示例
    
```json
{
  "Action": "GetUMInferTokenUsageResponse",
  "Data": {},
  "RetCode": 0
}
```





