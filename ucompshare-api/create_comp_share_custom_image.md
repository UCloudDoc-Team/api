# 制作算力平台实例自制镜像 - CreateCompShareCustomImage

## 简介

制作算力平台实例自制镜像






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateCompShareCustomImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UHostId** | string | 实例Id |**Yes**|
| **Name** | string | 镜像名称。不允许与账号下其他镜像名称重复 |**Yes**|
| **Description** | string | 镜像描述信息 |No|
| **Softwares.Framework** | string | 镜像框架名称 |No|
| **Softwares.FrameworkVersion** | string | 镜像框架版本 |No|
| **Softwares.CUDAVersion** | string | 镜像CUDA版本 |No|
| **Softwares.Application.N** | string | 【array of string】镜像的应用列表 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CompShareImageId** | string | 镜像Id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateCompShareCustomImage
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=QfXHFhNz
&UHostId=nssdsCyy
&Name=LzFDIvHG
&Description=qAvVvCqz
&Framework=yEJGEqBU
&Softwares=lsiQzNmp
&Softwares.FrameworkVersion=KbwCglSD
&Softwares.CUDAVersion=eUBiuDoa
&Softwares.Application.N=PNHDfYlQ
```

### 响应示例
    
```json
{
  "Action": "CreateCompShareCustomImageResponse",
  "CompShareImageId": "AGOGXcQQ",
  "RetCode": 0
}
```





