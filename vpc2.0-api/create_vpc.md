# 创建VPC-CreateVPC

创建VPC

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|Name|string|VPC名称|**Yes**|
|Network.n|string|VPC网段|**Yes**|
|Tag|string|业务组名称|No|
|Remark|string|备注|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|VPCId|string|VPC资源Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateVPC
&ProjectId=org-XXXX
&Region=cn-sh2
&Name=test
&Network.0=10.1.0.0/16
&Tag=test
&Remark=test
```

# Response Example
```
{
    "Action": "CreateVPCResponse", 
    "VPCId": "uvnet-XXXXXX", 
    "RetCode": 0
}
```

