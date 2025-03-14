# 修改令牌配置 - UpdateURocketMQToken

## 简介

修改拥有对于实例下Topic进行细粒度管控的公私钥配置。









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateURocketMQToken`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **TokenId** | string | 令牌ID |**Yes**|
| **TopicProducePerm** | string | Topic生产权限 |**Yes**|
| **TopicConsumePerm** | string | Topic消费权限 |**Yes**|
| **ServiceId** | string | 实例ID |**Yes**|
| **AllowProduceTopicList** | string | 允许生产的Topic名称数组 |No|
| **AllowConsumeTopicList** | string | 允许消费的Topic名称数组 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateURocketMQToken
&Region=cn-zj
&ProjectId=AANdeSPt
&TokenId=MhJQodGQ
&TopicProducePerm=aMHYSCwN
&TopicConsumePerm=nvxazmUJ
&ServiceId=tqjQzpYU
&AllowProduceTopicList=cBgUESqS
&AllowConsumeTopicList=MhbKXyTB
```

### 响应示例
    
```json
{
  "Action": "UpdateURocketMQTokenResponse",
  "Message": "UqhTOmmn",
  "RetCode": 0
}
```





