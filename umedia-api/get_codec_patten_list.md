# 获取转码模版列表-GetCodecPattenList

获取转码模版列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DefaultPattenList|array|系统预制的转码模版列表,详细结构见下表|No|
|CustomizedPattenList|array|客户定制的转码模版列表，详细结构见下表|No|

## CodecPattenListNode
|Parameter name|Type|Description|Required|
|---|---|---|---|
|PattenId|string|模版的ID|**Yes**|
|PattenName|string|模版名称,长度不查过256个字节|**Yes**|
|DestVideoBitrate|string|视频码率，单位kbps。|**Yes**|
|DestVideoResolution|string|视频分辨率，格式为像素宽度x像素高度，例如1280x720。该字段为空表示保持原始视频大小。|**Yes**|
|DestVideoCodec|string|视频的编码类型|**Yes**|
|DestAudioBitrate|int|音频码率，单位kbps。|**Yes**|
|DestAudioSample|int|音频采样率，单位hz。|**Yes**|
|DestAudioChannel|int|音频声道数量。|**Yes**|
|DestFormat|string|目标视频格式，可选值为mp4、flv、mpegts。|**Yes**|
|DestSuffix|string|目标视频的文件名后缀。|**Yes**|
|CallbackUrl|string|转码任务结束后，回调客户的url地址。|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetCodecPattenList
```

# Response Example
```
{
    "Action": "GetCodecPattenListResponse", 
    " CustomizedPattenList": [], 
    "RetCode": 0, 
    "DefaultPattenList": [
        {
            "DestAudioSample ": 44100, 
            "DestVideoResolution ": "864x480", 
            "DestAudioBitrate ": 48, 
            "PattenName": "默认480p-mp4", 
            "DestAudioChannel ": 2, 
            "DestVideoBitrate ": 500, 
            "PattenId": "1", 
            "DestFormat ": "mp4", 
            "DestSuffix": "_480p", 
            "CallbackUrl": ""
        }
    ]
}
```

