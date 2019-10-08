# 导入工作流定义-CreateSFWorkflowFromTemplate

导入工作流定义

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Namespace|string|需要创建的工作流namespace|**Yes**|
|WorkflowName|string|需要创建的工作流名称|**Yes**|
|Workflow|string|描述工作流定义的base64字符串|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回消息|**Yes**|
|Version|int|	创建的工作流版本号|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateSFWorkflowFromTemplate
&Region=cn-zj
&ProjectId=pAZhEbkU
&Namespace=fdhoGtKK
&WorkflowName=hKfCxTNZ
&Workflow=bUaIPfzZ
```

# Response Example
```
{
    "Action": "CreateSFWorkflowFromTemplateResponse", 
    "Message": "success", 
    "Version": 3, 
    "RetCode": 0
}
```

