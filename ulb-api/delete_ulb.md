# 删除负载均衡-DeleteULB

删除负载均衡实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|ULBId|string|负载均衡实例的ID|**Yes**|
|ReleaseEip|bool|删除ulb时是否释放绑定的EIP，false标识只解绑EIP，true表示会释放绑定的EIP，默认是false|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteULB
&Region=cn-bj2
&ProjectId=project-XXXX
&ULBId=ulb-XXXX
&ReleaseEip=true
```

# Response Example
```
{
    "Action": "DeleteULBResponse", 
    "RetCode": 0
}
```

