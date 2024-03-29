# 更新应用型负载均衡实例属性 - UpdateLoadBalancerAttribute

## 简介

更新一个应用型负载均衡实例的属性






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateLoadBalancerAttribute)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateLoadBalancerAttribute`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **LoadBalancerId** | string | 负载均衡实例的ID |**Yes**|
| **Name** | string | 负载均衡实例的名称，不传则默认不修改 |No|
| **Tag** | string | 负载均衡实例所属的业务组ID，不传则默认不修改 |No|
| **Remark** | string | 负载均衡实例的备注信息，不传则默认不修改，限定字符长度：[0-255] |No|
| **AccessLogConfig.Enabled** | boolean | （应用型专用）是否开启访问日志记录功能 |No|
| **AccessLogConfig.US3BucketName** | string | （应用型专用）用于存储访问日志的bucket |No|
| **AccessLogConfig.US3TokenId** | string | （应用型专用）上传访问日志到bucket所需的token |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateLoadBalancerAttribute
&Region=oUNeUSea
&ProjectId=OsREyyef
&ULBId=GkUBRkMw
&Name=lZYAOAgX
&Tag=DEbbnUOn
&Remark=CBIPpanT
&EnableLog=6
&BucketName=HSqYYxUY
&TokenName=EUygHoyL
&TokenId=eVkfEqZv
&IsWAFOn=nlgFGfwX
```

### 响应示例
    
```json
{
  "Action": "UpdateLoadBalancerAttributeResponse",
  "RetCode": 0
}
```





