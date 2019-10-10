# 计划删除密钥-ScheduleKeyDeletion

计划删除密钥 进入计划删除列表 可调用CancelScheduleKeyDeletion恢复

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|KeyId|string|需要查看的主密钥对应的 KeyId|**Yes**|

```
UCloud管理密钥 不能删除。
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Status|string| 操作结果|**Yes**|
|RequestUuid|string|此次请求唯一标识符|No|

# Request Example
```
https://api.ucloud.cn/?Action=ScheduleKeyDeletion
&ProjectId=org-mjwvpk
&KeyId=ukms-xkxxse
```

# Response Example
```
{
    "Status": "success", 
    "Action": "ScheduleKeyDeletionResponse", 
    "RetCode": 0, 
    "RequestUuid": "18726098-1996-4d68-9661-052e3662bae3"
}
```

