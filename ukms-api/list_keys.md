# 获取主密钥列表-ListKeys

查询用户的主密钥信息列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Offset|int|输出列表起始位置，默认从0开始|No|
|Limit|int|输出列表数量,默认返回200个|No|
|OrderBy|string|列表排序方式, 可选项: "-created_time", "created_time", "type","-type"。默认按-type 密钥托管类型降序排列|No|

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
https://api.ucloud.cn/?Action=ListKeys
&ProjectId=org-mjwvpk
&OrderBy=-created_time
&Limit=10
&Offset=1
```

# Response Example
```
{
    "Status": "success", 
    "RetCode": 0, 
    "TotalCount": 1, 
    "Objects": [
        {
            "CreatedTime": 1545046660, 
            "LastModifiedTime": 1545046660, 
            "KeyId": "e675e01060b748488d9c58eb5a8e0701", 
            "Enabled": true, 
            "Description": "test description"
        }, 
        {
            "CreatedTime": 1544781647, 
            "LastModifiedTime": 1544781647, 
            "KeyId": "1765de4951b9470bab6758c3838806fa", 
            "Enabled": true, 
            "Description": "test description"
        }
    ], 
    "Action": "ListKeysResponse", 
    "RequestUuid": "7180ba66-bc0a-45af-9789-37e6ed04763b"
}
```

