# 按使用场景列出框架和应用 - ListUHadoopFrameworkAppByUseCase

## 简介

按使用场景列出uhadoop的框架和框架中的应用






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUHadoopFrameworkAppByUseCase)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUHadoopFrameworkAppByUseCase`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AppConfigSet** | array[[*AppConfigVersion*](#AppConfigVersion)] | 使用场景的app版本信息 |No|

#### 数据模型


#### AppConfigVersion

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ReleaseVersion** | string | UHadoop版本，值为 uhadoop 3.0\|uhadoop 2.2\|uhadoop 3.1 |No|
| **HadoopVersion** | string | Hadoop版本，值为 hadoop3.2.1-udh3.0\|hadoop3.3.4-udh3.1 \|hadoop2.8.5-udh2.2 |No|
| **Framework** | string | 框架，值为'Hadoop'\|'HDFS'\|'MR'\|'StarRocks'之一,框架，例如Hadoop\|MR\|HDFS\|StarRocks Hadoop框架包含存储与计算服务 MR集群包含计算服务 HDFS只包含存储服务,StarRocks为StarRocks集群 |No|
| **FrameworkVersion** | string | 框架版本 |No|
| **UseCases** | array[[*UseCases*](#UseCases)] | 框架示例 |No|

#### UseCases

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Case** | string | 集群种类 |No|
| **MustHas** | string | 依赖的组件 |No|
| **AppVersion** | string | 组件版本 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUHadoopFrameworkAppByUseCase
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=DiNeHnVU
&UDDPFramework=kPowpBNb
```

### 响应示例
    
```json
{
  "Action": "ListUHadoopFrameworkAppByUseCaseResponse",
  "AppConfigSet": [
    "VwmMcZHY",
    "WYFBVhLP",
    "gsacbJyM",
    "JvBrgtyR"
  ],
  "Message": "EhOqvoCy",
  "RetCode": 0
}
```





