# 获取转码任务详情 - GetCodecTaskDetail

## 简介

获取转码任务详情






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetCodecTaskDetail)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCodecTaskDetail`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **TaskId** | string | 任务的id号 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TaskId** | string | 任务ID |No|
| **SrcUrl** | string | 原始视频url地址 |No|
| **DestVideoName** | string | 输出文件名 |No|
| **DestBucket** | string | 输出文件的存储空间 |No|
| **DestFormat** | string | 输出视频封装格式 |No|
| **Duration** | int | 视频时长，单位：秒。只有当任务状态为处理完成时，该参数有意义，其他状态该参数为0。 |No|
| **CodecPattenDetail** | [*CodecPattenDetail*](#CodecPattenDetail) | CodecPattenDetail类型 |No|
| **WatermarkDetail** | [*WatermarkDetail*](#WatermarkDetail) | WatermarkDetail类型 |No|
| **CodecLevel** | string | 转码清晰度：superdefinition、highdefinition、mediumdefinition、lowdefinition，分别对应计费的4种规格。只有当任务状态为处理完成时，该参数有意义，其他状态该参数为空字符串。 |No|
| **CreateTime** | int | 任务创建时间，单位：Unix时间戳 |No|
| **FinishTime** | int | 任务完成时间，单位：Unix时间戳。当任务状态为排队中或者处理中时，该参数为0。 |No|
| **Status** | string | 任务状态：waiting、processing、finished、failed，分别表示排队中，处理中，处理完成，处理失败。 |No|
| **CallbackUrl** | string | 任务完成后回调客户的url地址。 |No|

#### 数据模型


#### CodecPattenDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CodecPattenId** | string | 转码模版ID |**Yes**|
| **CodecPattenName** | string | 转码模版名称 |**Yes**|
| **DestFormat** | string | 输出视频格式 |**Yes**|
| **DestVideoBitrate** | int | 输出文件视频码率 |**Yes**|
| **DestVideoResolution** | string | 输出文件分辨率 |**Yes**|
| **DestSuffix** | string | 输出文件后缀 |**Yes**|
| **DestVideoCodec** | string | 视频编码类型 |**Yes**|

#### WatermarkDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **WatermarkId** | string | 任务ID |**Yes**|
| **WatermarkName** | string | 水印名称 |**Yes**|
| **WaterMarkType** | string | image表示图片水印，text表示文字水印 |**Yes**|
| **ImageUrl** | string | 图片水印的url地址，只有图片水印有该字段。 |**Yes**|
| **TextContent** | string | 文字水印内容 |**Yes**|
| **Position** | string | 水印的参考位置，topleft、topright、center、bottomleft、bottomright分别表示左上、右上、居中、左下、右下 |**Yes**|
| **PaddingX** | int | 水印离最近的水平边线占整个视频宽度的百分比，取值[0-49] |No|
| **PaddingY** | int | 水印离最近的垂直边线占整个视频高度的百分比,取值[0-49] |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCodecTaskDetail&TaskId=1265
```

### 响应示例
    
```json
{
  "Action": "GetCodecTaskDetailResponse",
  "CallbackUrl": "",
  "CodecLevel": "mediumdefinition",
  "CodecPattenDetail": {
    "CodecPattenId": "11",
    "CodecPattenName": "高清-864x480-mpegts",
    "DestFormat": "mpegts",
    "DestSuffix": "_480p",
    "DestVideoBitrate": 500,
    "DestVideoResolution": "864x480"
  },
  "CreateTime": 1501149123,
  "DestBucket": "wangqiguox.cn-bj.ufileos.com",
  "DestFormat": "mpegts",
  "DestVideoName": "1080p-1080p_480p.ts",
  "Duration": 300,
  "FinishTime": 1501149289,
  "RetCode": 0,
  "SrcUrl": "http://bushu.cn-bj.ufileos.com/1080p-1080p.ts",
  "Status": "finished",
  "TaskId": "1265",
  "WatermarkDetail": {}
}
```





