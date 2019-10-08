# 更新弹性IP属性-UpdateEIPAttribute

更新弹性IP名称，业务组，备注等属性字段

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|EIPId|string|EIP资源ID|**Yes**|
|Name|string|名字（Name Tag Remark都为空则报错）|No|
|Tag|string|业务|No|
|Remark|string|备注|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
http(s)://api.spark.ucloud.cn/?Action=UpdateEIPAttribute
&Region=cn-bj2
&EIPId=eip-w2pew1
&Name=test
&Tag=test
&Remark=test
```

# Response Example
```
{
    "Action": "UpdateEIPAttributeResponse", 
    "RetCode": 0
}
```

