# 获取镜像tag-GetImageTag

获取镜像tag

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|RepoName|string|镜像仓库名称|**Yes**|
|ImageName|string|镜像名称|**Yes**|
|Offset|int|偏移量，默认0|No|
|Limit|int|每次获取数量，默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|tag总数|**Yes**|
|TagSet|array|tag列表|**Yes**|

## TagSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TagId|int|标签ID|**Yes**|
|Name|string|标签名称|**Yes**|
|Description|string|标签描述|**Yes**|
|UpdateTime|int|更新时间|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetImageTag
&ProjectId=PYFWFOHm
&RepoName=ZPGYodrQ
&ImageName=EpDfWhyI
&Offset=4
&Limit=6
&ProjectId=EiCgAvZy
```

# Response Example
```
{
    "Action": "GetImageTagResponse", 
    "TotalCount": 3, 
    "RetCode": 0, 
    "TagSet": [
        {
            "UpdateTime": "JuCcdSiy", 
            "TagName": "WAIUkrwN"
        }, 
        {
            "UpdateTime": "uCNRUKaI", 
            "TagName": "cMPKnfJc"
        }
    ]
}
```

