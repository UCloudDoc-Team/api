# 获取镜像列表-DescribeImage

获取指定数据中心镜像列表，用户可通过指定操作系统类型，镜像Id进行过滤。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ImageType|string|镜像类型。标准镜像：Base，镜像市场：Business， 自定义镜像：Custom，默认返回所有类型|No|
|OsType|string|操作系统类型：Linux， Windows 默认返回所有类型|No|
|ImageId|string|镜像Id|No|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回数据长度，默认为20|No|
|PriceSet|int|是否返回价格：1返回，0不返回；默认不返回|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的镜像总数|No|
|ImageSet|array|镜像列表详见 UHostImageSet|No|

## UHostImageSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ImageId|string|镜像ID|No|
|ImageName|string|镜像名称|No|
|Zone|string|可用区，参见 [可用区列表](api/summary/regionlist) \||No|
|OsType|string|操作系统类型：Liunx，Windows|No|
|OsName|string|操作系统名称|No|
|ImageType|string|镜像类型 标准镜像：Base， 行业镜像：Business，自定义镜像：Custom|No|
|Features|array|特殊状态标识， 目前只有[NetEnhnced]（高包量机型）|No|
|FuncType|string|行业镜像类型（仅行业镜像将返回这个值）|No|
|IntegratedSoftware|string|集成软件名称（仅行业镜像将返回这个值）|No|
|Vendor|string|供应商（仅行业镜像将返回这个值）|No|
|Links|string|介绍链接（仅行业镜像将返回这个值）|No|
|State|string|镜像状态， 可用：Available，制作中：Making， 不可用：Unavailable|No|
|ImageDescription|string|镜像描述|No|
|CreateTime|int|创建时间，格式为Unix时间戳|No|
|ImageSize|int|镜像大小|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeImage
&Region=cn-bj2
&Zone=cn-bj2-04
&ImageType=Base
&OsType=Windows
```

# Response Example
```
{
    "Action": "DescribeImageResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "ImageSet": [
        {
            "Zone": "cn-bj2-04", 
            "ImageDescription": "Windows Server 2008 R2 Datacenter 32-bit", 
            "OsName": "Windows 2008 32 位", 
            "ImageId": "0b560b1d-f3b1-43de-a492-08875d79211b", 
            "State": "Available", 
            "ImageName": " Windows 2008 32 位", 
            "OsType": "Windows", 
            "CreateTime": 1234567890, 
            "ImageType": "Base"
        }
    ]
}
```

