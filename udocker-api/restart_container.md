# 重启容器-RestartContainer

重启容器

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ContainerId|string|要重启的容器ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=RestartContainer
&Region=cn-bj2
&ProjectId=org-xxx
&ContainerId=docker-xxx
```

# Response Example
```
{
    "Action": "RestartContainerResponse", 
    "RetCode": 0
}
```

