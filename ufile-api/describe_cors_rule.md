# 获取跨域规则信息 - DescribeCORSRule

## 简介

获取跨域规则信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeCORSRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeCORSRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **BucketName** | string | Bucket名称 |**Yes**|
| **CORSId** | string | 跨域规则ID，不指定则返回所有跨域规则信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*CORSRuleSet*](#CORSRuleSet)] | 跨域规则信息集合 |**Yes**|

#### 数据模型


#### CORSRuleSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AllowedOrigin** | string | 指定允许的跨域请求的来源，使用通配符(*)表示允许所有来源的跨域请求（多个Origin用‘,’分隔） |**Yes**|
| **AllowedMethod** | string | 指定允许的跨域请求方法。支持的方法名有：GET、PUT、POST、DELETE、HEAD、OPTIONS（多个Method用‘,’分隔） |**Yes**|
| **CORSId** | string | 跨域规则id |**Yes**|
| **CreateTime** | int | 跨域规则创建时间 |**Yes**|
| **ModifyTime** | int | 跨域规则最新修改时间 |**Yes**|
| **AllowedHeader** | string | 指定允许的跨域请求头（多个Header用‘,’分隔） |**Yes**|
| **ExposeHeader** | string | 指定允许用户从应用程序中访问的响应头（多个ExposeHeader用‘,’分隔） |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeCORSRule
&BucketName=vKqZsPWy
&CORSId=zAjPoFbr
&ProjectId=BqlWTeMK
```

### 响应示例
    
```json
{
  "Action": "DescribeCORSRuleResponse",
  "DataSet": [
    {
      "AllowedHeader": "rRdVitUa",
      "AllowedMethod": "OoNanzZo",
      "AllowedOrigin": "uUeaGfwz",
      "CreateTime": 2,
      "ExposeHeader": "fxknMzKB",
      "MaxAgeSeconds": 7,
      "ModifyTime": 7
    }
  ],
  "RetCode": 0
}
```





