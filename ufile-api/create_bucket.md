# 创建Bucket - CreateBucket

## 简介

创建Bucket

?> －BucketName BucketName参数将构成域名的一部分(与Bucket默认关联的域名为<BucketName>.ufile.ucloud.cn)，必须具有全局唯一性。 BucketName参数必须符合Bucket名称规范,规范如下: (1) 长度在3\~63字节之间； (2) 可以由多个标签组成，各个标签用 . 间隔，每个标签只能包含小字母、数字、连接符（短横线），并且标签的开头和结尾的字符只能是小写字母或数字； (3) 不可以是IP地址。



## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateBucket)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateBucket`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **BucketName** | string | 待创建Bucket的名称，具有全局唯一性 |**Yes**|
| **Type** | string | Bucket访问类型，public或private; 默认为private |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BucketName** | string | 已创建Bucket的名称 |No|
| **BucketId** | string | 已创建Bucket的ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateBucket
&BucketName=blue
&Type=public
&Region=cn-bj2
```

### 响应示例
    
```json
{
  "Action": "CreateBucketResponse",
  "BucketId": "ufile-xxx",
  "BucketName": "blue",
  "Retcode": 0
}
```





