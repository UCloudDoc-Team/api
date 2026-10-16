# 获取令牌信息 - GetURocketMQToken

## 简介

获取令牌信息。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetURocketMQToken`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ServiceId** | string | 实例ID |**Yes**|
| **TokenId** | string | Token Id |**Yes**|
| **Display** | string | 是否显示明文 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Token** | [*Token*](#Token) | 令牌 |**Yes**|

#### 数据模型


#### Token

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AllowProduceTopicList** | string | 允许生产的Topic名称数组 |**Yes**|
| **AllowConsumeTopicList** | string | 允许消费的Topic名称数组 |**Yes**|
| **AKSK** | [*AKSK*](#AKSK) | 密钥 |**Yes**|
| **TokenId** | string | 令牌ID |**Yes**|
| **TopicProducePerm** | string | Topic生产权限 |**Yes**|
| **TopicConsumePerm** | string | 	<br />Topic消费权限 |**Yes**|
| **ServiceId** | string | 	<br />Service ID |**Yes**|
| **Name** | string | 令牌名称 |**Yes**|
| **Type** | string | 令牌类型 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **ModifyTime** | int | 修改时间 |**Yes**|

#### AKSK

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AccessKey** | string | 公钥 |**Yes**|
| **SecretKey** | string | 私钥 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetURocketMQToken
&Region=cn-zj
&ProjectId=iaptzNZw
&ServiceId=nSItBJFC
&TokenId=pYYzopwa
&Display=true
```

### 响应示例
    
```json
{
  "Action": "GetURocketMQTokenResponse",
  "Message": "LdUjHjhe",
  "RetCode": 0,
  "Token": {}
}
```





