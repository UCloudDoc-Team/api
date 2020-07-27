# 获取截图任务详情 - GetSnapTaskDetail

## 简介

获取截图任务详情






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetSnapTaskDetail)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetSnapTaskDetail`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **TaskId** | string | 查询的截图任务ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SrcUrl** | string | 原始视频url地址 |No|
| **SnapType** | string | 截图模式，single表示确定时间点单张截图，periodic表示周期截图,dynamic表示为gif截图 |No|
| **ImageName** | string | 截图输出的文件名（这里指基础图片的文件名，不包括后缀） |No|
| **ImageFormat** | string | 图片格式类型 |No|
| **ImageCount** | int | 截图张数，只有任务状态处理完成时值才有意义。 |No|
| **DestBucket** | string | 存储图片的ufile的bucket名称 |No|
| **CreateTime** | int | 任务创建时间，单位：Unix时间戳 |No|
| **FinishTime** | int | 任务结束时间，单位：Unix时间戳。只有任务状态为处理完成时值才有意义，默认为0。 |No|
| **Status** | string | 任务状态：waiting、processing、finished、failed，分别表示排队中，处理中，处理完成，处理失败。 |No|
| **ImageList** | string | 文件名列表 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetSnapTaskDetail&TaskId=1
```

### 响应示例
    
```json
{
  "Action": "GetSnapTaskDetailResponse",
  "CreateTime": 1496298697,
  "DestBucket": "video.cn-bj.ufileos.com",
  "FinishTime": 1496298900,
  "ImageCount": 5,
  "ImageFormat ": "jpg",
  "ImageList": [
    "myvideo_0.jpg",
    "myvideo_1.jpg",
    "myvideo_2.jpg",
    "myvideo_3.jpg",
    "myvideo_4.jpg"
  ],
  "ImageName": "myvideo.jpg",
  "RetCode": 0,
  "SnapType": "periodic",
  "SrcUrl": "http://video.ucloud.cn/myvideo.mp4",
  "Status": "finished",
  "TaskId": "1"
}
```





