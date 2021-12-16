# 获取盒子摄像头推流列表 - GetSdnboxCameraList

## 简介

获取盒子摄像头推流列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetSdnboxCameraList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SdnboxCamera** | array[[*SdnboxCamera*](#SdnboxCamera)] | 摄像头推流列表 |**Yes**|

#### 数据模型


#### SdnboxCamera

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | string | 盒子ID |No|
| **Name** | string | 盒子名称 |No|
| **Camera** | array[[*CameraStream*](#CameraStream)] | 摄像头流信息列表 |No|

#### CameraStream

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ID** | string | 摄像头ID |No|
| **Name** | string | 摄像头名称 |No|
| **Status** | int | 推流状态 |No|
| **VideoParams** | string | 视频参数 |No|
| **SmallPullRTMPAddress** | string | 小窗口视频拉流地址 |No|
| **PullRTMPAddress** | [*PullRTMPAddress*](#PullRTMPAddress) | 拉流地址, 是 map 格式, key 是流类型, value是地址 |No|
| **IsOnline** | boolean | 摄像头是否在线 |No|

#### PullRTMPAddress

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Rtmp** | string |  |No|
| **Flv** | string |  |No|
| **Hls** | string |  |No|
| **Dash** | string |  |No|
| **Webrtc** | string |  |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetSdnboxCameraList
```

### 响应示例
    
```json
{
  "Message": "GetSdnboxCameraListResponse",
  "RetCode": 0,
  "SdnboxCamera": [
    {
      "Camera": [
        {
          "ID": "01",
          "Name": "01",
          "PullRTMPAddress": {
            "dash": "http://113.31.163.86:8080/dash/uaccessbox-jtjy2rx2_01_stream/index.mpd",
            "flv": "http://113.31.163.86:8080/live?app=50913519\u0026stream=uaccessbox-jtjy2rx2_01_stream",
            "hls": "http://113.31.163.86:8080/hls/uaccessbox-jtjy2rx2_01_stream/index.m3u8",
            "rtmp": "rtmp://113.31.163.86:1935/50913519/uaccessbox-jtjy2rx2_01_stream"
          },
          "PushRTMPAddress": "rtmp://113.31.163.86:1935/50913519/uaccessbox-jtjy2rx2_01_stream",
          "SmallPullRTMPAddress": null,
          "Status": 1,
          "VideoParams": "{\"pixel_format\":\"YUYV\",\"resolution\":\"1080*720;640*480\"}"
        },
        {
          "ID": "02",
          "Name": "02",
          "PullRTMPAddress": {
            "dash": "http://113.31.163.86:8080/dash/uaccessbox-jtjy2rx2_02_stream/index.mpd",
            "flv": "http://113.31.163.86:8080/live?app=50913519\u0026stream=uaccessbox-jtjy2rx2_02_stream",
            "hls": "http://113.31.163.86:8080/hls/uaccessbox-jtjy2rx2_02_stream/index.m3u8",
            "rtmp": "rtmp://113.31.163.86:1935/50913519/uaccessbox-jtjy2rx2_02_stream"
          },
          "PushRTMPAddress": "rtmp://113.31.163.86:1935/50913519/uaccessbox-jtjy2rx2_02_stream",
          "SmallPullRTMPAddress": null,
          "Status": 1,
          "VideoParams": "{\"pixel_format\":\"YUYV\",\"resolution\":\"640*480\"}"
        }
      ],
      "ID": "uaccessbox-jtjy2rx2",
      "Name": "middle-1"
    }
  ]
}
```





