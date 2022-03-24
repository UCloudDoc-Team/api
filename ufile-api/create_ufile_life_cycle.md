# 创建生命周期管理 - CreateUFileLifeCycle

## 简介

创建生命周期管理






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUFileLifeCycle)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUFileLifeCycle`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **LifeCycleName** | string | 生命周期名称 |**Yes**|
| **Prefix** | string | 生命周期所适用的前缀；*为整个存储空间文件；一条规则只支持一个文件前缀； |**Yes**|
| **Status** | string | Enabled -- 启用，Disabled -- 不启用 |**Yes**|
| **BucketName** | string | 存储空间名称 |**Yes**|
| **Days** | int | 指定一个过期天数N，文件会在其最近更新时间点的N天后过期，自动删除；参数范围：[7,36500]，0代表不启用 |No|
| **ArchivalDays** | int | 指定一个过期天数N，文件会在其最近更新时间点的N天后，自动变为归档存储类型；参数范围：[7,36500]，0代表不启用 |No|
| **IADays** | int | 指定一个过期天数N，文件会在其最近更新时间点的N天后，自动变为低频存储类型；参数范围：[7,36500]，0代表不启用 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LifeCycleId** | string | 生命周期Id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUFileLifeCycle
&Region=cn-gd
&ProjectId=orf-sdfssd
&LifeCyCleName=lifecycle
&Prefix=test-
&Days=10
&Status=Enabled
&BucketName=lifecycle-test1
&ArchivalDays=1
&ArchivalDays=6
&IADays=2
```

### 响应示例
    
```json
{
  "Action": "CreateUFileLifeCycleResponse",
  "LifeCycleId": "dc7eca04-edbc-4ae9-aefd-816253123456",
  "RetCode": 0
}
```





