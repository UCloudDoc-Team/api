# 模型仓库模型列表 - DescribeModelRepositoryModels

## 简介

模型仓库模型列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeModelRepositoryModels`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Name** | string | 模型名称 |No|
| **Tags** | string | 模型标签列表, 标签之间英文逗号:"," 相连接 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Models** | array[[*ModelRepositoryModel*](#ModelRepositoryModel)] | 模型信息列表 |**Yes**|

#### 数据模型


#### ModelRepositoryModel

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CreateTime** | int | 创建时间 |No|
| **Name** | string | 模型名称 |No|
| **Path** | string | 模型路径 |No|
| **Tag** | string | 模型标签 |No|
| **Size** | string | 模型大小 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeModelRepositoryModels
&Region=cn-zj
&Zone=cn-zj-01
&Name=XuTihRix
&Tags=BRfYrTYl
```

### 响应示例
    
```json
{
  "Action": "DescribeModelRepositoryModelsResponse",
  "Models": [
    "lfOTCZZx"
  ],
  "RetCode": 0
}
```





