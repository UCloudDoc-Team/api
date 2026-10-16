# 获取转码配置 - GetULiveTranscodeConfigInfo

## 简介

获取转码配置






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetULiveTranscodeConfigInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetULiveTranscodeConfigInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Domain** | string | 域名 |**Yes**|
| **App** | string | 接入点 |**Yes**|
| **TemplateName.N** | string | 模版名称数组，输入参数需要TemplateName.n的格式输入，例如：TemplateName.0,TemplateName.1;分别代表数组中第一个和第二个元素。如果不填此参数，则获取所有模版 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TemplateInfo** | array[[*TemplateInfo*](#TemplateInfo)] | 模版详细信息 |No|

#### 数据模型


#### TemplateInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TemplateName** | string | 模版名称 |**Yes**|
| **Vcodec** | string | 视频编码格式 |**Yes**|
| **Resolution** | string | Resolution |**Yes**|
| **BitrateControl** | string | 码率控制 |**Yes**|
| **Vbitrate** | string | 视频码率 |**Yes**|
| **Fps** | string | 视频帧率 |**Yes**|
| **Gop** | string | Gop |**Yes**|
| **Profile** | string | 画质 |**Yes**|
| **Vpreset** | string | Vpreset |**Yes**|
| **IsProhibitSmallToLarge** | boolean | 是否配置开启禁止小转大，true代表开启、false代表未开启 |**Yes**|
| **IsResolutionSelfAdaptation** | boolean | 是否配置开启是否横竖屏短边自适应，true代表开启、false代表未开启 |**Yes**|
| **IsSeiPassThrough** | boolean | 是否配置sei透传，true代表开启、false代表未开启 |**Yes**|
| **Acodec** | string | 音频编码格式 |**Yes**|
| **Abitrate** | string | 音频码率 |**Yes**|
| **AsamplingRate** | string | 音频采样率 |**Yes**|
| **Msg** | string | 枚举值：success、not exist、failure（成功、模板不存在、失败） |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetULiveTranscodeConfigInfo
&ProjectId=mCHofbav
&Domain=uiQxqkzy
&App=tgwySkkF
&TemplateName.n=XxuBdRQC
```

### 响应示例
    
```json
{
  "Action": "GetULiveTranscodeConfigInfoResponse",
  "RetCode": 0,
  "TemplateInfo": [
    {
      "Abitrate": "ZYYOTgSw",
      "Acodec": "BMAXWXNm",
      "AsamplingRate": "QncuflJX",
      "BitrateControl": "KQNdeUUd",
      "Fps": "yBPnAHyk",
      "Gop": "kfXpcnFl",
      "IsProhibitSmallToLarge": "EFnRyxLS",
      "IsResolutionSelfAdaptation": "xZUxADQv",
      "IsSeiPassThrough": "OPcNoyuw",
      "Msg": "uouuJIOV",
      "Profile": "THsTrEPH",
      "Resolution": "HVStfPyI",
      "TemplateName": "UOGWmuor",
      "Vbitrate": "pwxvEwLv",
      "Vcodec": "WqoCJMru",
      "Vpreset": "QrDHpMrK"
    }
  ]
}
```





