# 取消计划删除密钥-CancelScheduleKeyDeletion

取消计划删除密钥

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|KeyId|string|需要查看的主密钥对应的 KeyId|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Status|string| 操作结果|**Yes**|
|RequestUuid|string|此次请求唯一标识符|No|

# Request Example
```
https://api.ucloud.cn/?Action=CancelScheduleKeyDeletion
&ProjectId=CNGdnvTQ
&KeyId=nfxhOYNv
```

# Response Example
```
{
    "Status": "success", 
    "RequestUuid": "xxxx--yyyy-z90033", 
    "Action": "CancelScheduleKeyDeletionResponse", 
    "RetCode": 0
}
```

