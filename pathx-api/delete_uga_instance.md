# 删除全球加速服务加速配置-DeleteUGAInstance

删除全球加速服务加速配置

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID,如org-xxxx。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UGAId|string|全球加速实例ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUGAInstance
&UGAAId=tsypfqQP
```

# Response Example
```
{
    "Action": "DeleteUGAInstanceResponse", 
    "RetCode": 0
}
```

