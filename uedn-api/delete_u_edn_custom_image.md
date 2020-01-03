# 删除UEDN客户自定义镜像-DeleteUEdnCustomImage

删除UEDN客户自定义镜像

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ImageId|string|镜像ID|**Yes**|
|IdcId|string|机房ID，带机房ID表示只删除指定机房镜像|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ImageId|string|镜像ID|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUEdnCustomImage
&ProjectId=fNzaIQOu
&ImageId=sUQCPUdv
&IdcId=hKQJjPXi
```

# Response Example
```
{
    "Action": "DeleteUEdnCustomImageResponse", 
    "RetCode": 0, 
    "ImageId": "LETXRJBS"
}
```

