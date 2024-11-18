# 创建功能模板 - CreateFunctionTemplate

## 简介

创建功能参数模板






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
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
| **Function** | string | 功能名称：<br />- VideoTranscode ，视频转码；<br />- VideoCapture，视频截帧 |**Yes**|
| **ContainerFormat** | string | VideoTranscode，文件输出格式：<br />- mp4<br />        - flv<br />        - mpegts<br />        - webm<br />        - avi |**Yes**|
| **EncodeFormat** | string | VideoTranscode，编码格式：<br />- H.264<br />        - H.265<br />        - VPX<br />        - VPX-VP9 |**Yes**|
| **VideoBitRate** | string | VideoTranscode，视频比特率(Kbps)：<br />- custom<br />- adpative |No|
| **VideoBitRateCustom** | string | VideoTranscode，自定义视频比特率：<br />最小值：10<br />最大值：50000 |No|
| **Resolution** | string | VideoTranscode，分辨率(px)：<br />- custom<br />- origin |No|
| **ResolutionWidth** | string | VideoTranscode，分辨率宽：<br />最小值：160<br />最大值：1920 |No|
| **ResolutionHeight** | string | VideoTranscode，分辨率高：<br />最小值：160<br />最大值：1920 |No|
| **AudioBitRate** | string | VideoTranscode，音频比特率：<br />- custom<br />- 48<br />- 64<br />- 128<br />- 160 |No|
| **AudioBitRateCustom** | string | VideoTranscode，自定义音频比特率<br />最小值：8<br />最大值：1000 |No|
| **AudioSampleRate** | string | VideoTranscode，音频采样率（Hz）：<br />- 22050<br />- 32000<br />- 44100<br />- 48000 |No|
| **AudioChannel** | string | VideoTranscode，音频声道：<br />- one<br />- two<br /> |No|
| **CRF** | string | VideoTranscode，CRF压缩率：<br /> - custom<br /> - 15<br /> - 22<br /> - 30 |No|
| **CRFCustom** | string | VideoTranscode，自定义CRF压缩率：<br />最小值：0<br />最大值：51 |No|
| **FrameRate** | string | VideoTranscode，帧率(fps)：<br />- custom<br />- 25<br /> |No|
| **FrameRateCustom** | string | VideoTranscode，自定义帧率：<br />最小值：0<br />最大值：60 |No|
| **ImageFormat** | string | VideoCapture，截帧图片格式：<br />- jpg<br />- png<br />- gif |No|
| **SnapTime** | string | VideoCapture，截帧时间点（s）：<br />- custom<br />- 0<br />- 1<br />- 2<br /><br /> |No|
| **SnapTimeCustom** | int | VideoCapture，自定义截帧时间点：<br />最小值：0<br />最大值：10000 |No|
| **ImageWidth** | string | VideoCapture，截帧图片宽度:<br />- custom<br />- 640<br /> |No|
| **ImageWidthCustom** | int | VideoCapture，自定义截帧图片宽度：<br />最小值：0<br />最大值：10000 |No|
| **ImageHeight** | string | VideoCapture，截帧图片高度：<br />- custom<br />- 480<br /> |No|
| **ImageHeightCustom** | int | VideoCapture，自定义截帧图片高度：<br />最小值：16<br />最大值：2160 |No|
| **GifFrameRate** | string | VideoCapture，截帧gif图片帧率，仅支持gif格式（fps）<br />- custom<br />- 480<br /> |No|
| **GifFrameRateCustom** | int | VideoCapture，自定义截帧gif图片帧率(fps)：<br />最小值：16<br />最大值：2160 |No|
| **GifTime** | string | VideoCapture，gif图片持续时间，仅支持gif格式（s）：<br />- custom<br />- 1<br />- 5<br />- 10 |No|
| **GifTimeCustom** | int | VideoCapture，自定义gif图片持续时间：<br />最小值：1<br />最大值：60 |No|

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
&ProjectId=ufBujOaM
&ProjectName=SjmoGIoy
&TemplateName=EOfHEyfM
&Function=ZuITdyRm
&ContainerFormat=DvYRFLDz
&EncodeFormat=tRvXGSer
&VideoBitRate=djNutdvr
&VideoBitRateCustom=dKiRweEa
&Resolution=aCsaFYAL
&ResolutionWidth=vEbnJKsm
&ResolutionHeight=osgSsfWt
&AudioBitRate=fCCtrwEq
&AudioBitRateCustom=OhaBBaRd
&AudioSampleRate=bEeXxREl
&AudioChannel=cpIXNuVm
&CRF=aAkMhnjG
&CRFCustom=WpcGrDzQ
&FrameRate=StvwDpzm
&FrameRateCustom=NRxLeYwF
&ImageFormat=OAwWrJMT
&SnapTime=fFOVfGIX
&SnapTimeCustom=7
&ImageWidth=ebxPdalN
&ImageWidthCustom=6
&ImageHeight=SCfbCrYH
&ImageHeightCustom=9
&GifFrameRate=bpgGLGBn
&GifFrameRateCustom=4
&GifTime=sBIHeuch
&GifTimeCustom=6
```

### 响应示例
    
```json
{
  "Action": "CreateFunctionTemplateResponse",
  "RetCode": 0,
  "TemplateId": "ZSKXihoc"
}
```





