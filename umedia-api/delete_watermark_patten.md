# 删除水印模版-DeleteWatermarkPatten

删除水印模版

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|PattenId|string|模版Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteWatermarkPatten
&PattenId=11
```

# Response Example
```
{
    "Action": "DeleteWatermarkPattenResponse", 
    "RetCode": 0
}
```

