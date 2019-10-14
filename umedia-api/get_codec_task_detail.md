# 获取转码任务详情-GetCodecTaskDetail

获取转码任务详情

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|TaskId|string|任务的id号|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TaskId|string|任务ID|No|
|SrcUrl|string|原始视频url地址|No|
|DestVideoName|string|输出文件名|No|
|DestBucket|string|输出文件的存储空间|No|
|DestFormat|string|输出视频封装格式|No|
|Duration|int|视频时长，单位：秒。只有当任务状态为处理完成时，该参数有意义，其他状态该参数为0。|No|
|CodecPattenDetail|object|CodecPattenDetail类型|No|
|WatermarkDetail|object|WatermarkDetail类型|No|
|CodecLevel|string|转码清晰度：superdefinition、highdefinition、mediumdefinition、lowdefinition，分别对应计费的4种规格。只有当任务状态为处理完成时，该参数有意义，其他状态该参数为空字符串。|No|
|CreateTime|int|任务创建时间，单位：Unix时间戳|No|
|FinishTime|int|任务完成时间，单位：Unix时间戳。当任务状态为排队中或者处理中时，该参数为0。|No|
|Status|string|任务状态：waiting、processing、finished、failed，分别表示排队中，处理中，处理完成，处理失败。|No|
|CallbackUrl|string|任务完成后回调客户的url地址。|No|

## CodecPattenDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CodecPattenId|string|转码模版ID|**Yes**|
|CodecPattenName|string|转码模版名称|**Yes**|
|DestFormat|string|输出视频格式|**Yes**|
|DestVideoBitrate|int|输出文件视频码率|**Yes**|
|DestVideoResolution|string|输出文件分辨率|**Yes**|
|DestSuffix|string|输出文件后缀|**Yes**|
|DestVideoCodec|string|视频编码类型|**Yes**|

## WatermarkDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|WatermarkId|string|任务ID|**Yes**|
|WatermarkName|string|水印名称|**Yes**|
|WaterMarkType|string|image表示图片水印，text表示文字水印|**Yes**|
|ImageUrl|string|图片水印的url地址，只有图片水印有该字段。|**Yes**|
|TextContent|string|文字水印内容|**Yes**|
|Position|string|水印的参考位置，topleft、topright、center、bottomleft、bottomright分别表示左上、右上、居中、左下、右下|**Yes**|
|PaddingX|int|水印离最近的水平边线占整个视频宽度的百分比，取值[0-49]|No|
|PaddingY|int|水印离最近的垂直边线占整个视频高度的百分比,取值[0-49]|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetCodecTaskDetail&TaskId=1265
```

# Response Example
```
{
    "FinishTime": 1501149289, 
    "Status": "finished", 
    "DestBucket": "wangqiguox.cn-bj.ufileos.com", 
    "RetCode": 0, 
    "WatermarkDetail": {}, 
    "CodecPattenDetail": {
        "CodecPattenName": "高清-864x480-mpegts", 
        "DestVideoBitrate": 500, 
        "DestVideoResolution": "864x480", 
        "CodecPattenId": "11", 
        "DestFormat": "mpegts", 
        "DestSuffix": "_480p"
    }, 
    "DestVideoName": "1080p-1080p_480p.ts", 
    "SrcUrl": "http://bushu.cn-bj.ufileos.com/1080p-1080p.ts", 
    "Action": "GetCodecTaskDetailResponse", 
    "TaskId": "1265", 
    "DestFormat": "mpegts", 
    "Duration": 300, 
    "CodecLevel": "mediumdefinition", 
    "CreateTime": 1501149123, 
    "CallbackUrl": ""
}
```

