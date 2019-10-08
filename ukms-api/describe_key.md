# 查看主密钥-DescribeKey

查看主密钥信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考GetProjectList接口|No|
|KeyId|string|需要查看的主密钥对应的 KeyId|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|KeyId|string|CMK 的唯一标识符|No|
|Alias|string|别名|No|
|Description|string|对密钥的描述说明|No|
|Enabled|bool|是否启用|No|
|CreatedTime|int|创建时间|No|
|LastModifiedTime|int|最后修改时间|No|
|Status|string|API执行状态|No|
|RequestUuid|string|API请求ID|No|
|Type|string|密钥类型，如ucloud_manage、self_manage|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeKey
&ProjectId=org-mjwvpk
&KeyId=ukms-oep2f0
```

# Response Example
```
{
    "Status": "success", 
    "KeyId": "ukms-xxxx", 
    "RetCode": 0, 
    "Alias": "vKdnnfCj", 
    "Enabled": true, 
    "Action": "DescribeKeyResponse", 
    "CreatedTime": 1, 
    "RequestUuid": "093399-ssxbcbc-3423444", 
    "LastModifiedTime": 7, 
    "Type": "CustomerManagedKeys", 
    "Description": "jXLaGikX"
}
```

