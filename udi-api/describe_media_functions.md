# 获取多媒体功能 - DescribeMediaFunctions

## 简介

描述当前支持的多媒体功能以及对应功能需要的参数信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeMediaFunctions)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeMediaFunctions`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Function** | string | 要查询的Function名称，为空则返回所有支持的Function |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Functions** | array[[*Function*](#Function)] | 功能列表 |No|

#### 数据模型


#### Function

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **FunctionName** | string |  |No|
| **DisplayName** | string |  |No|
| **InputType** | string |  |No|
| **OutputType** | string |  |No|
| **SupportParams** | array[[*ParamOption*](#ParamOption)] |  |No|

#### ParamOption

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DisplayName** | string |  |No|
| **ParamName** | string |  |No|
| **OptionalValues** | array[string] |  |No|
| **Required** | boolean |  |No|
| **WhenValueCustom** | array[[*ParamCustom*](#ParamCustom)] |  |No|

#### ParamCustom

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ParamName** | string |  |No|
| **ParamType** | string |  |No|
| **Max** | int |  |No|
| **Min** | int |  |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeMediaFunctions
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-ZtBadiGe
&Function=VideoTranscode
```

### 响应示例
    
```json
{
  "Action": "DescribeMediaFunctions",
  "Functions": [
    {
      "DisplayName": "视频转码",
      "FunctionName": "VideoTranscode",
      "InputType": "video",
      "OutputType": "video",
      "SupportParams": [
        {
          "DisplayName": "输出格式",
          "OptionalValues": [
            "mp4",
            "flv",
            "mpegts",
            "webm"
          ],
          "ParamName": "ContainerFormat",
          "Required": true
        },
        {
          "DisplayName": "编码格式",
          "OptionalValues": [
            "H.264",
            "H.265",
            "VPX",
            "VPX-VP9"
          ],
          "ParamName": "EncodeFormat",
          "Required": true
        },
        {
          "DisplayName": "视频码率(Kbps)",
          "OptionalValues": [
            "custom",
            "adpative"
          ],
          "ParamName": "VideoBitRate",
          "Required": false,
          "WhenValueCustom": [
            {
              "Max": 5000,
              "Min": 100,
              "OpenMax": false,
              "OpenMin": false,
              "ParamName": "VideoBitRateCustom",
              "ParamType": "int"
            }
          ]
        },
        {
          "DisplayName": "帧率(fps)",
          "OptionalValues": [
            "custom",
            "25",
            "30"
          ],
          "ParamName": "FrameRate",
          "Required": false,
          "WhenValueCustom": [
            {
              "Max": 60,
              "Min": 1,
              "OpenMax": false,
              "OpenMin": false,
              "ParamName": "FrameRateCustom",
              "ParamType": "int"
            }
          ]
        },
        {
          "DisplayName": "压缩率CRF",
          "OptionalValues": [
            "custom",
            "15",
            "22",
            "30"
          ],
          "ParamName": "CRF",
          "Required": false,
          "WhenValueCustom": [
            {
              "Max": 51,
              "OpenMax": false,
              "OpenMin": false,
              "ParamName": "CRFCustom",
              "ParamType": "int"
            }
          ]
        },
        {
          "DisplayName": "分辨率(px)",
          "OptionalValues": [
            "custom",
            "origin"
          ],
          "ParamName": "Resolution",
          "Required": false,
          "WhenValueCustom": [
            {
              "Max": 1920,
              "Min": 160,
              "OpenMax": false,
              "OpenMin": false,
              "ParamName": "ResolutionWidth",
              "ParamType": "int"
            },
            {
              "Max": 1920,
              "Min": 160,
              "OpenMax": false,
              "OpenMin": false,
              "ParamName": "ResolutionHeight",
              "ParamType": "int"
            }
          ]
        },
        {
          "DisplayName": "音频码率(Kbps)",
          "OptionalValues": [
            "custom",
            "48",
            "64",
            "128",
            "160"
          ],
          "ParamName": "AudioBitRate",
          "Required": false,
          "WhenValueCustom": [
            {
              "Max": 1000,
              "Min": 8,
              "OpenMax": false,
              "OpenMin": false,
              "ParamName": "AudioBitRateCustom",
              "ParamType": "int"
            }
          ]
        },
        {
          "DisplayName": "音频采样率(Hz)",
          "OptionalValues": [
            "22050",
            "32000",
            "44100",
            "48000"
          ],
          "ParamName": "AudioSampleRate",
          "Required": false
        },
        {
          "DisplayName": "音频声道",
          "OptionalValues": [
            "one",
            "two"
          ],
          "ParamName": "AudioChannel",
          "Required": false
        }
      ]
    }
  ],
  "RetCode": 0
}
```





