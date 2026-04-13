# 将自制镜像发布到镜像社区 - PublishCompShareImage

## 简介

将自制镜像发布到镜像社区






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `PublishCompShareImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **CompShareImageId** | string | 镜像Id |**Yes**|
| **Price** | float | 镜像价格。单位：元，支持00.00 |**Yes**|
| **Cover** | string | 封面。base64编码的图片 |No|
| **Tags.N** | string | 【array of string】镜像标签。最多支持3个标签 |No|
| **Description** | string | 镜像描述信息 |No|
| **Readme** | string | 镜像详情描述【富文本】 |No|
| **Softwares.Framework** | string | 镜像框架名称 |No|
| **Softwares.FrameworkVersion** | string | 镜像框架版本 |No|
| **Softwares.CUDAVersion** | string | 镜像CUDA版本 |No|
| **Softwares.Applications.N** | string | 镜像应用列表 |No|
| **CommunityImageName** | string | 发布社区镜像名称 |No|
| **AutoStart** | string | 是否支持自启动 false: 不支持 true:支持 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=PublishCompShareImage
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=jZiEoNMD
&CompShareImageId=JWknOdxV
&Price=7.93629
&Cover=MhkfzmsO
&Tags.N=TYAYjlon
&Description=RDKhWkGN
&Readme=zjJZTwpX
&Framework=tCSDcdKf
&Software=NHxOvdKu
&Software.FrameworkVersion=OAeZpQFI
&Software.CUDAVersion=ROpHCuaK
&Software.Applications.N=eYttDPIQ
&CommunityImageName=mDfdlBsQ
&AutoStart=ahmokIuL
```

### 响应示例
    
```json
{
  "Action": "PublishCompShareImageResponse",
  "NewCompShareImageId": "bHwPsHQn",
  "RetCode": 0
}
```





