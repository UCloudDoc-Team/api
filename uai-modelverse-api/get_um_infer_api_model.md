# 获取api模型列表 - GetUMInferAPIModel

## 简介

获取该apikey能调用api的模型列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUMInferAPIModel)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUMInferAPIModel`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list)   |**Yes**|
| **KeyId** | string | apikey 的id |No|
| **ModelType** | int | 模型类型，1: 文本生成，2: 图片生成。 |No|
| **SquareId** | string | 模型广场的id，用来跳转体验中心 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*UMinferAPIModel*](#UMinferAPIModel)] | 模型名称的字符串列表 |**Yes**|

#### 数据模型


#### UMinferAPIModel

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ServedModelName** | string | 使用OpenAI接口调用时，填入的 model值 |No|
| **Id** | string | id |No|
| **Name** | string | 名称 |No|
| **SimpleDescribe** | string | 描述 |No|
| **Language** | array[string] | 语言 |No|
| **Icon** | string | 图标链接 |No|
| **Pricing** | [*Pricing*](#Pricing) | 模型价格 |No|
| **CreateAt** | int | 创建时间 |No|
| **UpdateAt** | int | 更新时间 |No|

#### Pricing

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Completion** | float | 输出定价 |No|
| **Prompt** | float | 提示词定价 |No|
| **Image** | float | 生图定价 |No|
| **Currency** | string | 币种 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUMInferAPIModel
&KeyId=BNPXRmCb
&ModelType=2
&SquareId=fschGecL
&ProjectId=cauxjXmc
```

### 响应示例
    
```json
{
  "Action": "GetUMInferAPIModelResponse",
  "Data": [
    "daArfQcO"
  ],
  "RetCode": 0
}
```





