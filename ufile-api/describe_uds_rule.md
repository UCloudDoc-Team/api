# 获取解压缩规则信息 - DescribeUdsRule

## 简介

针对解压缩规则进行查询






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUdsRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUdsRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BucketName** | string | 源BucketName |**Yes**|
| **RuleId** | string | 规则ID，不设置时，查询改bucket的所有规则 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 此次删除的规则的ID |**Yes**|
| **DataSet** | array[string] | 规则数组 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUdsRule
&BucketName=“BucketName”
&RuleId="RuleId"
```

### 响应示例
    
```json
{
  "Action": "DescribeUdsRuleResponse",
  "DataSet": [
    "zivXZtSg"
  ],
  "Message": "fhLdrSPb",
  "RetCode": 0,
  "RuleId": "wyOlYNVU"
}
```





