# 网页防篡改更新指定url的缓存-UpdateAssurePageCache

网页防篡改更新指定url的缓存

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ID|int|待更新的防篡改页面ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateAssurePageCache
&ID=3
&ProjectId=ncrFEvrU
```

# Response Example
```
{
    "Action": "UpdateAssurePageCacheResponse", 
    "RetCode": 0
}
```

