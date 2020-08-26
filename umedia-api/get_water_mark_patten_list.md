# 获取水印模版列表 - GetWaterMarkPattenList

## 简介

获取水印模版列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetWaterMarkPattenList)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetWaterMarkPattenList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DefaultPattenList** | array[[*WaterMarkPattenListNode*](#WaterMarkPattenListNode)] | 水印模版列表,详细结构见下表 |No|
| **CustomizedPattenList** | array[[*WaterMarkPattenListNode*](#WaterMarkPattenListNode)] | 水印模版列表,详细结构见下表 |No|

#### 数据模型


#### WaterMarkPattenListNode

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PattenId** | string | 模版的ID |**Yes**|
| **PattenName** | string | 模版名称,长度不超过256个字节 |**Yes**|
| **WaterMarkType** | string | image表示图片水印，text表示文字水印 |**Yes**|
| **ImageUrl** | string | 图片水印的url地址，只有图片水印有该字段。 |**Yes**|
| **TextContent** | string | 文字水印的内容，只有文字水印有该字段。 |**Yes**|
| **FontType** | string | 字体类型，只有文字水印有该字段。 |**Yes**|
| **FontColor** | string | 字体颜色，只有文字水印有该字段。 |**Yes**|
| **FontSize** | int | 字体大小，单位：磅，只有文字水印有该字段。 |**Yes**|
| **Position** | string | 水印的参考位置，topleft、topright、center、bottomleft、bottomright分别表示左上、右上、居中、左下、右下 |**Yes**|
| **PaddingX** | int | 水印离最近的水平边线占整个视频宽度的百分比，取值[0-49] |**Yes**|
| **PaddingY** | int | 水印离最近的垂直边线占整个视频高度的百分比,取值[0-49] |**Yes**|
| **CallbackUrl** | string | 转码任务结束后，回调客户的url地址。 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetWaterMarkPattenList
```

### 响应示例
    
```json
{
  "Action": "GetWaterMarkPattenListResponse",
  "CustomizedPattenList": [
    {
      "CallbackUrl": "",
      "FontColor": "#c42222",
      "FontSize": 16,
      "FontType": "arial",
      "ImageUrl": "",
      "PaddingX": 0,
      "PaddingY": 0,
      "PattenId": "132",
      "PattenName": "shuip",
      "Position": "center",
      "TextContent": "呜呜呜呜-_ssa21212",
      "WaterMarkType": "text"
    }
  ],
  "DefaultPattenList": [
    {
      "CallbackUrl": "",
      "FontColor": "",
      "FontSize": 0,
      "FontType": "",
      "ImageUrl": "http://image",
      "PaddingX": 5,
      "PaddingY": 5,
      "PattenId": "2",
      "PattenName": "default_water",
      "Position": "",
      "TextContent": "",
      "WaterMarkType": "none"
    }
  ],
  "RetCode": 0
}
```





