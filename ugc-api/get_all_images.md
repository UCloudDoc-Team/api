# 获取所有的镜像名称-GetAllImages

获取所有可用的Docker镜像名称，包括公有和私有的。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ImageSet|array|JSON格式的Docker镜像列表|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetAllImages
&Region=cn-bj2
```

# Response Example
```
{
    "Action": "GetAllImagesResponse", 
    "ImageSet": [
        "library/harbor_ui:160615.8", 
        "library/harbor_ui:160615.9"
    ], 
    "Message": "", 
    "RetCode": 0
}
```

