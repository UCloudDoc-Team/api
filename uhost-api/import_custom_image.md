# 导入镜像 - ImportCustomImage

## 简介

把UFile的镜像文件导入到UHost，生成自定义镜像





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ImportCustomImage)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ImportCustomImage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **ImageName** | string | 镜像名称 |**Yes**|
| **UFileUrl** | string | UFile私有空间地址 |**Yes**|
| **OsType** | string | 操作系统平台，比如CentOS、Ubuntu、Windows、RedHat等，请参考控制台的镜像版本；若导入控制台上没有的操作系统，参数为Other |**Yes**|
| **OsName** | string | 操作系统详细版本，请参考控制台的镜像版本；OsType为Other时，输入参数为Other |**Yes**|
| **Format** | string | 镜像格式，可选RAW、VHD、VMDK、qcow2 |**Yes**|
| **Auth** | boolean | 是否授权。必须填true |**Yes**|
| **ImageDescription** | string | 镜像描述 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ImageId** | string | 镜像Id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ImportCustomImage
&Region=cn-bj2
&ProjectId=asdf
&ImageName=mbfThSeV
&UFileUrl=https://***.cn-bj.ufileos.com/***
&OsType=CentOS
&OsName=CentOS 6.5 32位
&Format=VMDK
&Auth=1
```

### 响应示例
    
```json
{
  "Action": "ImportCustomImageResponse",
  "ImageId": "uimage-xxxxx",
  "RetCode": 0
}
```





