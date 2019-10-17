# 创建副本-CreateUDBReplicationInstance

创建MongoDB的副本节点（包括仲裁）

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SrcId|string|primary节点的DBId,该值可以通过DescribeUDBInstance获取|**Yes**|
|Name|string|实例名称，至少6位|**Yes**|
|Port|int|端口号，默认27017，取值范围3306至65535。|No|
|IsArbiter|bool|是否是仲裁节点，默认false，仲裁节点按最小机型创建|No|
|UseSSD|bool|是否使用SSD，默认不使用|No|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DBId|string|创建从节点的DBId|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUDBReplicationInstance
&Region=cn-bj2
&SrcId=udb-xxxxx
&Name=mongodb-xxxxxxx-01
```

# Response Example
```
{
    "Action": "CreateUDBReplicationInstanceResponse", 
    "DBId": "udb-xxxxx", 
    "RetCode": 0
}
```

