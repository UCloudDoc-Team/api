# 添加域名白名单 - AddWafDomainWhiteList

## 简介

添加域名白名单





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddWafDomainWhiteList)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddWafDomainWhiteList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 	<br />项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 要添加白名单的域名 |**Yes**|
| **Source** | string | 白名单来源；可选值:用户自定义(custom)，机器行为检测(bot)，bot-rule |**Yes**|
| **CIDRS.N** | string | IP、网段或者IP段，传递数组 |**Yes**|
| **Name** | string | 名称 |No|
| **Remark** | string | 备注信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Id** | int | 添加成功后返回的域名白名单ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddWafDomainWhiteList
&ProjectId=org-xxx
&FullDomain=www.test.com
&Source=custom
&Type=custom
&CIDRS.0=2.2.2.2/28
&Name=test
&Remark=test
```

### 响应示例
    
```json
{
  "Action": "AddWafDomainWhiteListResponse",
  "Id": 2,
  "RetCode": 0
}
```





