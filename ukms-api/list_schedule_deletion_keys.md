# 获取计划删除密钥列表-ListScheduleDeletionKeys

获取计划删除密钥列表，调用ScheduleKeyDeletion命令后进入此列表， 默认30天后正式删除。正式删除前可调用CancelScheduleKeyDeletion恢复

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Offset|int|输出列表起始位置，默认从0开始|No|
|Limit|int|输出列表数量，默认返回200个|No|
|OrderBy|string|列表排序方式, 可选项: "-created_time", "created_time","plan_delete_time","-plan_delete_time";默认按-plan_delete_time 计划删除时间升序返回|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Objects|array|主密钥信息组成的列表|**Yes**|
|Status|string|操作结果|No|
|RequestUuid|string|请求唯一标识符|No|
|TotalCount|int|符合条件的总数, 不同于Limit|No|

## CMK
|Parameter name|Type|Description|Required|
|---|---|---|---|
|KeyId|string|CMK 的唯一标识符|**Yes**|
|Type|string|密钥类型，仅支持UCloudManagedKeys、CustomerManagedKeys。默认值CustomerManagedKeys|**Yes**|
|Description|string|对密钥的描述说明|**Yes**|
|Enabled|bool|是否启用|**Yes**|
|CreatedTime|int|创建时间 时间戳|**Yes**|
|LastModifiedTime|int|最后修改时间 时间戳|**Yes**|
|Alias|string|别名，与CMK一一对应|No|
|PlanDeleteTime|int|计划删除时间 时间戳|No|

# Request Example
```
https://api.ucloud.cn/?Action=ListScheduleDeletionKeys
&ProjectId=tHNjmJFy
&Offset=2
&Limit=1
&OrderBy=fmNDDFOg
```

# Response Example
```
{
    "Status": "success", 
    "RetCode": 0, 
    "TotalCount": 8, 
    "Objects": [
        {
            "CreatedTime": 2, 
            "LastModifiedTime": 3, 
            "KeyId": "ukms-xxxx", 
            "Enabled": true, 
            "Description": "JZLFkWFu"
        }
    ], 
    "Action": "ListScheduleDeletionKeysResponse", 
    "RequestUuid": "31232123-xxxx-eyy455"
}
```

