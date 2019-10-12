# UGA与UPath解绑-UGAUnBindUPath

UGA与UPath解绑

```
将加速配置于加速线路解绑后  加速效果会很快消失，请确认您的操作 是否会影响业务
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UGAId|string|加速配置实例ID 格式uga-xxx|**Yes**|
|UPathId|string|加速线路实例ID 格式upath-xxx|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UGAUnBindUPath
&ProjectId=org-xxx
&UGAId =uga-xxx
&UPathId=upath-xxxx
```

# Response Example
```
{
    "Action": "UGAUnBindUPathResponse", 
    "RetCode": 0
}
```

