# 创建水印模版-CreateWatermarkPatten

创建水印模版

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|PattenName|string|模版名称,长度不查过256个字节|**Yes**|
|WaterMarkType|string|image表示图片水印，text表示文字水印|**Yes**|
|Position|string|水印的参考位置，topleft、topright、center、bottomleft、bottomright分别表示左上、右上、居中、左下、右下|**Yes**|
|PaddingX|int|水印离最近的水平边线占整个视频宽度的百分比，取值[0-49]|**Yes**|
|PaddingY|int|水印离最近的垂直边线占整个视频高度的百分比,取值[0-49]|**Yes**|
|ImageUrl|string|图片水印的url地址|No|
|TextContent|string|文字水印的内容|No|
|FontType|string|字体类型,中文支持仿宋、黑体、楷体、宋体、微软雅黑，英文字体支持arial、verdana、georgia、times new roman。注意如果水印内容含有中文，则必须使用中文字体。|No|
|FontColor|string|字体颜色，可使用颜色英文单词，如red、green来表示，也可使用RGB十六进制颜色，比如FF0000|No|
|FontSize|int|字体大小，单位：磅，取值范围[8-48]|No|
|CallbackUrl|string|转码任务结束后，回调客户的url地址。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PattenId|string|创建成功后生成的转码模版ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateWatermarkPatten
&PattenName=我的水印
&WaterMarkType=image
&ImageUrl=https://image.ucloud.cn/my.jpg
&Position= topleft
&PaddingX=5
&PaddingY=5
```

# Response Example
```
{
    "Action": " CreateWatermarkPattenResponse", 
    "PattenId": "123", 
    "RetCode": 0
}
```

