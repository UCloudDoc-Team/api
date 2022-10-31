# 更新解压缩规则 - UpdateUdsRule

## 简介

针对对象存储的文件，进行自动触发解压。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateUdsRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateUdsRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RuleId** | string | 规则的唯一Id |**Yes**|
| **RuleName** | string | 规则名称 |**Yes**|
| **SrcBucket** | string | 源Bucket名字，全局唯一 |**Yes**|
| **SrcTokenId** | string | 源bucket的token之一的tokenId |**Yes**|
| **DstBucket** | string | 目标Bucket名字，全局唯一 |**Yes**|
| **DstTokenId** | string | 目标bucket的token之一的tokenId |**Yes**|
| **DstDirectory** | string | 解压后的目标目录 |**Yes**|
| **KeepUS3Name** | boolean | 是否以压缩文件的前缀为最后一层目录 |**Yes**|
| **Prefixes** | string | 触发解压缩的前缀 |**Yes**|
| **Ops.N** | string | 操作的ops数组,"Ops.0":"unzip" |No|
| **Events.N** | string | 通知的事件数组 |No|
| **ContactGroupId** | string | 联系的用户组ID |No|
| **NotificationTypes.N** | string | 通知的类型数组 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RuleId** | string | 返回规则的规则ID |**Yes**|
| **Mesage** | string | 该请求的消息成功或者失败的描述 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateUdsRule
&RuleId="RuleId"
&RuleName="name"
&SrcBucketName="SrcBucketName"
&SrcTokenId="SrcTokenId"
&DstBucketName=“DstBucketName”
&DstTokenId="DstTokenId"
&DstDirectory="KeepUS3Name"
&KeepUS3Name=false
&Prefixes="Prefixes"
&Ops.n="Ops.0"
&Events.n="Events.0"
&ContactGroupId="ContactGroupId"
&NotificationTypes.n="NotificationTypes.0"
&RuleName="RuleName"
```

### 响应示例
    
```json
{
  "Action": "UpdateUdsRuleResponse",
  "Mesage": "fElcUBax",
  "RetCode": 0,
  "RuleId": "RuleId"
}
```





