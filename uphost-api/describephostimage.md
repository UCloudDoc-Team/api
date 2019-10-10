# 获取物理机镜像-DescribePHostImage

获取物理云主机镜像列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ImageType|string|镜像类别，枚举为：Base,标准镜像；默认为标准镜像。|No|
|ImageId.n|string|镜像ID|No|
|Offset|int|数据偏移量，默认为0|No|
|Limit|int|返回数据长度，默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的镜像总数|No|
|ImageSet|array|镜像列表 PHostImageSet|No|

## PHostImageSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ImageId|string|镜像ID|No|
|ImageName|string|镜像名称|No|
|OsName|string|操作系统名称|No|
|OsType|string|操作系统类型|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribePHostImage
&ProjectId=org1
&Region=cn-bj2
&Zone=cn-bj2-04
```

# Response Example
```
{
    "Action": "DescribePHostImageResponse", 
    "Images": [
        {
            "OsType": "Ubuntu", 
            "ImageName": " Ubuntu 12.04 64\u4f4d", 
            "OsName": "Ubuntu 12.04 64\u4f4d", 
            "ImageId": "pimg-yg-f2634b"
        }
    ], 
    "RetCode": 0
}
```

