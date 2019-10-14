# 删除全球加速服务加速配置-DeleteUGAInstance

删除全球加速服务加速配置

!> 删除加速配置实例时，建议先调用UGAUnbindUPath接口解绑线路 解绑成功后再删除

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID,如org-xxxx。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UGAId|string|加速配置实例ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|消息提示|No|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUGAInstance
&ProjectId=org-xxx
&UGAId=uga-xxxx
```

# Response Example
```
{
    "Action": "DeleteUGAInstanceResponse", 
    "Message": "", 
    "RetCode": 0
}
```

