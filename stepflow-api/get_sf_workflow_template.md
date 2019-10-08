# 导出工作流定义-GetSFWorkflowTemplate

导出工作流定义

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|WorkflowId|string|被导出工作流的Id|**Yes**|
|WorkflowVersion|int|被导出工作流的版本号。取值范围：WorkflowVersion >= 1；默认会获取发布版本对应的workflow；超过最大版本会返回错误|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|WorkflowId|string|导出工作流的Id|**Yes**|
|Version|int|导出工作流的版本号|**Yes**|
|Workflow|object|工作流定义，详细信息见工作流对象定义|**Yes**|
|Message|string|返回消息|No|

## WorkflowTemplate
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Input|array|工作流的输入，详细信息见Param|No|
|Output|array|工作流的输出，详细信息见Param|No|
|Activites|array|工作流的Activities，详细信息见工作流的Activity定义|No|

## Param
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Name|string|参数名称|No|
|Type|string|参数类型|No|
|Value|string|参数值|No|

## ActivityTemplate
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Name|string|Activity的名字|No|
|Type|string|Activity的类型|No|
|RetryTimes|string|	Activity的重试次数|No|
|Timeout|string|Activity的超时时间|No|
|Next|string|下一个Activity的名字|No|
|Input|object|Activity的输入|No|
|Output|array|Activity的输出，详见Param|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetSFWorkflowTemplate 
&Region=cn-bj2
&ProjectId=pAZhEbkU
&WorkflowId=fdhoGtKK
&WorkflowVersion=1
```

# Response Example
```
{
    "WorkflowId": "craig-qq4nqG.import_case_low", 
    "RetCode": 0, 
    "Workflow": {
        "Input": [
            {
                "Constrain": null, 
                "Type": "INT64", 
                "Name": "UserID", 
                "Value": ""
            }, 
            {
                "Constrain": null, 
                "Type": "STRING", 
                "Name": "UserName", 
                "Value": ""
            }
        ], 
        "Activities": [
            {
                "Name": "start", 
                "RetryTimes": 0, 
                "Next": "step934", 
                "Timeout": 600000, 
                "Output": null, 
                "Input": null, 
                "Type": "StartActivity"
            }, 
            {
                "Name": "end", 
                "RetryTimes": 0, 
                "Next": "", 
                "Timeout": 600000, 
                "Output": null, 
                "Input": null, 
                "Type": "EndActivity"
            }, 
            {
                "Name": "step934", 
                "RetryTimes": 0, 
                "Next": "end", 
                "Timeout": 600000, 
                "Output": null, 
                "Input": {
                    "body": {
                        "UserName": "${workflow.input.UserName}", 
                        "UserID": "${workflow.input.UserID}"
                    }, 
                    "url": "http://52.165.220.33/api/json/est/now", 
                    "retrytimes": 0, 
                    "header": {
                        "ContentType": "application/json"
                    }, 
                    "isAsync": false, 
                    "timeout": 0, 
                    "query": {
                        "Action": "VerifyUser"
                    }, 
                    "method": "GET"
                }, 
                "Type": "HttpActivity"
            }
        ], 
        "Output": []
    }, 
    "Version": 1, 
    "Action": "GetSFWorkflowTemplateResponse", 
    "Message": "success"
}
```

