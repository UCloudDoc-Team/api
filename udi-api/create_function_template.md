# 创建功能模板 - CreateFunctionTemplate

## 简介

创建功能参数模板






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateFunctionTemplate)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateFunctionTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ProjectName** | string | 项目名称 |**Yes**|
| **TemplateName** | string | 模板名称 |**Yes**|
| **Function** | string | 功能名称 |**Yes**|
| **ContainerFormat** | string | 文件输出格式 |**Yes**|
| **EncodeFormat** | string | 编码格式 |**Yes**|
| **VideoBitRate** | string | 视频比特率 |No|
| **VideoBitRateCustom** | string | 自定义视频比特率 |No|
| **Resolution** | string | 分辨率 |No|
| **ResolutionWidth** | string | 分辨率宽 |No|
| **ResolutionHeight** | string | 分辨率高 |No|
| **AudioBitRate** | string | 音频比特率 |No|
| **AudioBitRateCustom** | string | 自定义音频比特率 |No|
| **AudioSampleRate** | string | 音频采样率 |No|
| **AudioChannel** | string | 音频声道 |No|
| **CRF** | string | CRF压缩率 |No|
| **CRFCustom** | string | 自定义CRF压缩率 |No|
| **FrameRate** | string | 帧率 |No|
| **FrameRateCustom** | string | 自定义帧率 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TemplateId** | string | 创建的模板ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateFunctionTemplate
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=NhtMBsFV
&TemplateName=cNNXkXqJ
&Function=BDZwgwYv
&Params.ContainerFormat=RSCuDgtt
&Params.EncodeFormat=dxvflnQs
&Params.VideoBitRate=BvdxGqCI
&Params.VideoBitRateCustom=sDLUQRuk
&Params.Resolution=YYOZedPO
&Params.ResolutionWidth=sFXKXcib
&Params.ResolutionHeight=FyVXoEgl
&Pararms.AudioBitRate=aOelwEmH
&Params.AutioBitRateCustom=tSYykdBX
&Params.AudioSampleRate=LLtimVja
&Params.AudioChannel=VMVdOCPW
&Params.CRF=EYUXbbos
&Params.CRFCustom=QIAHDFFx
&Params.FrameRate=AgjYJGUG
&Params.FrameRateCustom=gytvsgHF
&ProjectName=eTdZleDT
```

### 响应示例
    
```json
{
  "Action": "CreateFunctionTemplateResponse",
  "ErrMsg": "AUeaDGlT",
  "RetCode": 0,
  "TemplateId": "DwaaQzrO"
}
```





