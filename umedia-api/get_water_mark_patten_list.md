# 获取水印模版列表-GetWaterMarkPattenList

获取水印模版列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DefaultPattenList|array|水印模版列表,详细结构见下表|No|
|CustomizedPattenList|array|水印模版列表,详细结构见下表|No|

## WaterMarkPattenListNode
|Parameter name|Type|Description|Required|
|---|---|---|---|
|PattenId|string|模版的ID|**Yes**|
|PattenName|string|模版名称,长度不超过256个字节|**Yes**|
|WaterMarkType|string|image表示图片水印，text表示文字水印|**Yes**|
|ImageUrl|string|图片水印的url地址，只有图片水印有该字段。|**Yes**|
|TextContent|string|文字水印的内容，只有文字水印有该字段。|**Yes**|
|FontType|string|字体类型，只有文字水印有该字段。|**Yes**|
|FontColor|string|字体颜色，只有文字水印有该字段。|**Yes**|
|FontSize|int|字体大小，单位：磅，只有文字水印有该字段。|**Yes**|
|Position|string|水印的参考位置，topleft、topright、center、bottomleft、bottomright分别表示左上、右上、居中、左下、右下|**Yes**|
|PaddingX|int|水印离最近的水平边线占整个视频宽度的百分比，取值[0-49]|**Yes**|
|PaddingY|int|水印离最近的垂直边线占整个视频高度的百分比,取值[0-49]|**Yes**|
|CallbackUrl|string|转码任务结束后，回调客户的url地址。|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetWaterMarkPattenList
```

# Response Example
```
{
    "Action": "GetWaterMarkPattenListResponse", 
    "CustomizedPattenList": [
        {
            "WaterMarkType": "text", 
            "FontColor": "#c42222", 
            "ImageUrl": "", 
            "TextContent": "\u545c\u545c\u545c\u545c-_ssa21212", 
            "FontType": "arial", 
            "PaddingY": 0, 
            "PaddingX": 0, 
            "PattenId": "132", 
            "Position": "center", 
            "FontSize": 16, 
            "PattenName": "shuip", 
            "CallbackUrl": ""
        }
    ], 
    "RetCode": 0, 
    "DefaultPattenList": [
        {
            "WaterMarkType": "none", 
            "FontColor": "", 
            "ImageUrl": "http://image", 
            "TextContent": "", 
            "FontType": "", 
            "PaddingY": 5, 
            "PaddingX": 5, 
            "PattenId": "2", 
            "Position": "", 
            "FontSize": 0, 
            "PattenName": "default_water", 
            "CallbackUrl": ""
        }
    ]
}
```

