# 获取物理机业务组-DescribePHostTags

获取物理机tag列表（业务组）

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|string|Tag的个数|No|
|TagSet|array|具体参见 PHostTagSet|No|

## PHostTagSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Tag|string|业务组名称|No|
|TotalCount|int|该业务组中包含的主机个数|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribePHostTags
&projectId=562
&Region=cn-bj2
&Zone=cn-bj2-04
```

# Response Example
```
{
    "Action": "DescribePHostTagsResponse", 
    "TotalCount": 10, 
    "RetCode": 0, 
    "TagSet": [
        {
            "TotalCount": "5", 
            "Tag": "Default"
        }
    ]
}
```

