# 删除自制镜像-TerminateCustomImage

删除用户自定义镜像

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ImageId|string|自制镜像ID 参见 [DescribeImage](describe_image.html)|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ImageId|string|自制镜像Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=TerminateCustomImage
&Region=cn-bj2
&Zone=cn-bj2-04
&ImageId=6fa91ff8-663c-4a7c-b054-1824aa41a1a3
```

# Response Example
```
{
    "Action": "TerminateCustomImageResponse", 
    "RetCode": "0"
}
```

