# 获取镜像列表-GetUvodnImage

uodn2.0

!> 无

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ImageType|string|镜像类型：1标准镜像，2行业镜像，3自定义镜像|No|
|Offset|int|数据偏移量，默认0，非负整数|No|
|Limit|int|返回数据长度， 默认20，非负整数|No|

?> 无

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ImageList|array|获取的镜像信息，具体参考下面ImageInfo|No|
|TotalCount|int|镜像总数|No|

## ImageInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ImageId|string|镜像ID|No|
|ImageName|string|镜像名称|No|
|ImageType|string|镜像类型：1标准镜像，2行业镜像，3自定义镜像|No|
|OcType|string|系统类型：unix, windows|No|
|ImageDesc|string|镜像描述|No|
|State|string|镜像状态：镜像状态 1可用，2不可用|No|
|ImageSize|string|镜像大小，单位GB|No|
|CreateTime|string|镜像创建时间戳|No|
|DeployInfoList|array|部署详情列表|No|

## DeployImageInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IdcId|string|机房ID|No|
|State|int|镜像状态 1-可用, 2-不可用, 3-获取中, 4-转换中, 5-部署中|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUvodnImage
&ProjectId=org-xxx
&ImageType=1
```

# Response Example
```
{
    "Action": "GetUvodnImageResponse", 
    "TotalCount": 1, 
    "ImageList": [
        {
            "OcType": "CentOs", 
            "ImageName": "CentOS 7.2 64位", 
            "ImageType": 1, 
            "ImageId": "uodn-image-xxx"
        }
    ], 
    "RetCode": 0
}
```

