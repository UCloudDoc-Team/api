# 删除镜像 - DeleteImage

## 简介

删除用户私有镜像，支持一次删除镜像多个tag，一次最多删除100个。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DeleteImage)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DeleteImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ImageName** | string | 私有镜像名，仅可以使用数字，字母，下划线，减号。 |**Yes**|
| **Tag.N** | string | tag名称，例如Tag.0代表希望删除Tag1，Tag.1代表希望删除Tag2。一次最多删除100个，从Tag.0到Tag.99 |**Yes**|
| **BucketName** | string | Bucket名称，仅可使用数字，字母，下划线。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DeleteImage
&BucketName=helloworld
&ImageName=image1
&PublicKey=6uRRmG67WK8KI9bBUv7Kw==fdsfsdfasdfdsafdsafdsafdsfdsafd
&Region=cn-bj2
&Tag.0=v0.1.20170602.1-test-DeleteImage40
&Tag.1=v0.1.20170602.1-test-DeleteImage41
&Signature=fsfdsfdsfsd602345e30b9f87fbc8c6e39f48d7dafa
```

### 响应示例
    
```json
{
  "Action": "DeleteImageResponse",
  "Message": "成功",
  "RetCode": 0
}
```





