# 获取可用地域-GetCleanServiceRegion

获取可用地域

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Area|string|[境内：domestic 境外：oversea 全部：all],默认all|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|CleanRegion|array|通过GetCleanServiceRegion 维护更新可用的地域列表以应对日益扩张的机房。截止至2019-01-24现网目前可用的列表如下：LosAngeles,Washington,Frankfurt,Singapore,Kaohsiung,Moscow,Tokyo,Taipei|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetCleanServiceRegion
&Area=[境内：domestic境外：oversea全部：all]
```

# Response Example
```
{
    "Action": "GetCleanServiceRegionResponse", 
    "Region": [
        "WNGYrBNW", 
        "ZjHmQKBk", 
        "BhsHKcGG", 
        "cYzABwdM", 
        "ArDRHDPs", 
        "OiAFIHNa", 
        "tMjFswFY", 
        "YFjoMQOL", 
        "NDcVohPo", 
        "tDXfVkhC"
    ], 
    "RetCode": 0
}
```

