# 创建自制镜像-CreateCustomImage

从指定UHost实例，生成自定义镜像。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|UHostId|string|UHost实例ID 参见 [DescribeUHostInstance](describe_uhost_instance.html)|**Yes**|
|ImageName|string|镜像名称|**Yes**|
|ImageDescription|string|镜像描述|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ImageId|string|镜像Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateCustomImage
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostId=uhost-qs20fr
&ImageName=Test
```

# Response Example
```
{
    "Action": "CreateCustomImageResponse", 
    "RetCode": "0"
}
```

