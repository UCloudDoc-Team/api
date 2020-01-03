# 修改镜像名称-ModifyUEdnImageName

修改镜像名称

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ImageId|string|镜像ID|**Yes**|
|ImageName|string|镜像名称|**Yes**|
|ImageDesc|string|镜像描述|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ImageId|string|镜像ID|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyUEdnImageName
&ProjectId=vNPKPpJa
&ImageId=olSztLZw
&ImageName=cNRyrZHq
&ImageDesc=UKejMZkn
```

# Response Example
```
{
    "Action": "ModifyUEdnImageNameResponse", 
    "RetCode": 0, 
    "ImageId": "REsCiJdd"
}
```

