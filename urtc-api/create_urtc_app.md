# 创建APP - CreateUrtcApp

## 简介

创建项目app(返回项目id)





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUrtcApp)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUrtcApp`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppName** | string | 创建的APP名称（不能为空） |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | 返回消息内容（成功succed,错误码不为0时，为具体提示内容） |**Yes**|
| **Data** | [*CreatAppModel*](#CreatAppModel) | 创建成功后返回的app基本信息（参数见CreatAppModel） |**Yes**|

#### 数据模型


#### CreatAppModel

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppName** | string | app名称 |**Yes**|
| **AppId** | string | appId |**Yes**|
| **AppStatue** | boolean | app状态(true:启用，false:停用) |**Yes**|
| **AppToken** | string | apptoken(接入rtc鉴权使用，妥善保管) |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUrtcApp
&AppName=qElRnmFQ
```

### 响应示例
    
```json
{
  "Action": "CreateUrtcAppResponse",
  "Data": {
    "AppId": "77d17d2f3f2b11e9b9ba00ff80725f6f",
    "AppName": "qElRnmFQ",
    "AppStatue": true,
    "AppToken": "fa3422b74ba211e9b10c00ff80725f6f"
  },
  "Msg": "Succed",
  "RetCode": 0
}
```





