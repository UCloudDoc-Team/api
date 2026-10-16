# 查询白名单 - DescribeExportLineRules

## 简介

查询白名单






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeExportLineRules)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeExportLineRules`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ResourceId** | string | UReach资源ID |No|
| **RuleType** | string | 白名单类型 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **WhiteListInfos** | array[[*WhiteListInfo*](#WhiteListInfo)] | 白名单信息 |**Yes**|

#### 数据模型


#### WhiteListInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RuleType** | string |  |No|
| **Name** | string |  |No|
| **Remark** | string |  |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeExportLineRules
&ProjectId=zchlfxWT
&ResourceId=XKFqHAZb
&RuleType=uLlscDuN
```

### 响应示例
    
```json
{
  "Action": "DescribeExportLineRulesResponse",
  "Message": "iRagdsqr",
  "RetCode": 0,
  "WhiteListInfos": [
    {
      "Name": "sJHOQRtd",
      "Remark": "WbiABVTq",
      "RuleType": "eUtoKvDD"
    }
  ]
}
```





