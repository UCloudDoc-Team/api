# 更新负载均衡属性-UpdateULBAttribute

更新ULB名字业务组备注等属性字段

```
Name Tag Remark 三个参数必传一个
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|ULBId|string|ULB资源ID|**Yes**|
|Name|string|名字|No|
|Tag|string|业务|No|
|Remark|string|备注|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
http://api.spark.ucloud.cn/?Action=UpdateULBAttribute
&Region=cn-bj2
&ProjectId=project-xs13ik
&ULBId=ulb-xjqquy
&Name=test
&Tag=test
&Remark=test
```

# Response Example
```
{
    "Action": "UpdateULBAttributeResponse", 
    "RetCode": 0
}
```

