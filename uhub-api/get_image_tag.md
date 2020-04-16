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
|TagName|string|默认不写，如果填写，代表查询该tag，否则查全部tag|No|

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
|UpdateTime|string|镜像更新时间|**Yes**|
|TagName|string|Tag名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetImageTag
&ProjectId=PYFWFOHm
&RepoName=ZPGYodrQ
&ImageName=EpDfWhyI
&Offset=4
&Limit=6
&ProjectId=EiCgAvZy
&TagName=mBJNxhdo
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

