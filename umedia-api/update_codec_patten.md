# 更新转码模版-UpdateCodecPatten

更新转码模版

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|PattenId|string|模板ID|**Yes**|
|PattenName|string|模版名称,长度不查过256个字节|**Yes**|
|DestVideoBitrate|int|视频码率，单位kbps,范围[200,4000]或者是0。如果为0，则表示由视频工厂输出自适应码率|**Yes**|
|DestVideoResolution|string|视频分辨率，格式为像素宽度x像素高度，例如1280x720。不传该字段则表示不改变分辨率|No|
|DestAudioBitrate|int|音频码率，单位kbps，范围[16,192]，默认使用48。|No|
|DestAudioSample|int|音频采样率，单位hz,可选值为22050、32000，44100，默认使用44100|No|
|DestAudioChannel|string|音频声道数量。可选值为1（单声道）、2（双声道），默认使用2（双声道）。|No|
|DestFormat|string|目标视频格式，可选值为mp4、flv、mpegts。|**Yes**|
|DestSuffix|string|目标视频的文件名后缀，长度不超过32个字符|**Yes**|
|CallbackUrl|string|转码任务结束后，回调客户的url地址。|No|
|DestVideoCodec|string|视频编码类型|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateCodecPatten
&PattenId=123
&PattenName=我的模版
&DestVideoBitrate=1200
&DestVideoResolution=1280x720
&DestAudioBitrate=48
&DestAudioSample=44100
&DestAudioChannel=2
&DestFormat=mp4
&DestSuffix=720p
```

# Response Example
```
{
    "Action": "UpdateCodecPattenResponse", 
    "RetCode": 0
}
```

