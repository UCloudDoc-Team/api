# 删除并停止WAF服务-StopWafService

删除并停止WAF服务

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|（废弃）地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|TransactionId|int|（废弃）资源唯一ID，从请求DescribeWafUserTransactionInfo中获取|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StopWafService
```

# Response Example
```
{
    "Action": "StopWafServiceResponse", 
    "RetCode": 0
}
```

