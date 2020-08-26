# 更新水印模版 - UpdateWatermarkPatten

## 简介

更新水印模版






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateWatermarkPatten)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateWatermarkPatten`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **PattenId** | string | 模版Id |**Yes**|
| **PattenName** | string | 模版名称,长度不查过256个字节 |**Yes**|
| **WaterMarkType** | string | image表示图片水印，text表示文字水印 |**Yes**|
| **Position** | string | 水印的参考位置，topleft、topright、center、bottomleft、bottomright分别表示左上、右上、居中、左下、右下 |**Yes**|
| **PaddingX** | int | 水印离最近的水平边线占整个视频宽度的百分比，取值[0-49] |**Yes**|
| **PaddingY** | int | 水印离最近的垂直边线占整个视频高度的百分比,取值[0-49] |**Yes**|
| **ImageUrl** | string | 图片水印的url地址 |No|
| **TextContent** | string | 文字水印的内容 |No|
| **FontType** | string | 字体类型,中文支持仿宋、黑体、楷体、宋体、微软雅黑，英文字体支持arial、verdana、georgia、times new roman。注意如果水印内容含有中文，则必须使用中文字体。 |No|
| **FontColor** | string | 字体颜色，可使用颜色英文单词，如red、green来表示，也可使用RGB十六进制颜色，比如FF0000 |No|
| **FontSize** | int | 字体大小，单位：磅，取值范围[8-48]。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateWatermarkPatten
&PattenId=11
&PattenName=我的水印
&WaterMarkType=image
&ImageUrl=https://image.ucloud.cn/my.jpg
&Position= topleft
&PaddingX=5
&PaddingY=5
```

### 响应示例
    
```json
{
  "Action": "UpdateWatermarkPattenResponse",
  "RetCode": 0
}
```





