# 修改bucket静态网页配置 - UpdateBucketStaticPageRule

## 简介

修改bucket静态网页配置






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateBucketStaticPageRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateBucketStaticPageRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Bucket** | string | 存储桶名称 |**Yes**|
| **Status** | string | 启用状态(enable/disable,只有绑定了自定义域名才能开启) |No|
| **DefaultIndex** | string | 默认首页 |No|
| **SubDirRedirect** | string | 子目录是否启用重定向 |No|
| **RuleFor404** | string | 404规则 |No|
| **DefaultPage404** | string | 404时的默认页面 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateBucketStaticPageRule
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=VKXDVtxD
&Bucket=bmGYdESd
&Status=MixZMOOG
&DefaultIndex=UcYGDuHX
&SubDirRedirect=oqAcAaFI
&RuleFor404=IwSpWHzs
&DefaultPage404=oxSvhzQy
```

### 响应示例
    
```json
{
  "Action": "UpdateBucketStaticPageRuleResponse",
  "RetCode": 0
}
```





