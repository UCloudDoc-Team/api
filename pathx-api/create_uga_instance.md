# 创建全球加速配置项 - CreateUGAInstance

## 简介

创建全球加速配置项

?> UGA作为加速配置实例，计费周期跟随绑定的UPath资源，资源到期自动续费，账户余额不足会产生欠费订单 直到资源被回收。如果没有绑定线路，加速配置不收取任何费用。

!> 加速配置创建完毕后 需要调用UGABindUPath接口才能使用


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUGAInstance)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUGAInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **Name** | string | 加速配置实例名称 |**Yes**|
| **IPList** | string | 加速源IP，多个IP用英文半角逗号(,)隔开；IPList和Domain二选一必填 |No|
| **Domain** | string | 加速源域名，IPList和Domain二选一必填 |No|
| **TCP.N** | string | TCP端口号，已废弃。请使用 CreateUGAForwarder API 创建端口 |No|
| **UDP.N** | string | UDP端口号，已废弃。请使用 CreateUGAForwarder API 创建端口 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGAId** | string | 加速配置ID |**Yes**|
| **CName** | string | 加速域名 用户可把业务域名CName到此域名上。注意：未绑定线路情况时 加速域名解析不出IP。 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUGAInstance
&Name=test
&Domain=google.com
```

### 响应示例
    
```json
{
  "Action": "CreateUGAInstanceResponse",
  "CName": "xxx.ucloudgda.com",
  "Message": "",
  "RetCode": 0,
  "UGAId": "uga-xxxx"
}
```





