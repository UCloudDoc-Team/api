# 删除转码模版-DeleteCodecPatten

删除转码模版

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|PattenId|string|模版Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteCodecPatten&PattenId=11
```

# Response Example
```
{
    "Action": "DeleteCodecPattenResponse", 
    "RetCode": 0
}
```

