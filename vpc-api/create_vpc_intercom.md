# 新建VPC互通 - CreateVPCIntercom

## 简介

新建VPC互通关系

?> 新建VPC互通关系




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateVPCIntercom)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateVPCIntercom`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 源VPC所在地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 源VPC所在项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **VPCId** | string | 源VPC短ID |**Yes**|
| **DstVPCId** | string | 目的VPC短ID |**Yes**|
| **DstRegion** | string | 目的VPC所在地域，默认与源VPC同地域。 |No|
| **DstProjectId** | string | 目的VPC项目ID。默认与源VPC同项目。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateVPCIntercom
&Region=cn-sh2
&ProjectId=org-XXXXX
&VPCId=uvnet-XXXXX
&DstRegion=cn-sh2
&DstProjectId=org-XXXX
&DstVPCId=uvnet-XXXX
```

### 响应示例
    
```json
{
  "Action": "CreateVPCIntercomResponse",
  "RetCode": 0
}
```





