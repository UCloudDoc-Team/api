# 更新配置-UpdateUDBParamGroup

更新UDB配置参数项

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|GroupId|int|配置参数组id，使用DescribeUDBParamGroup获得|**Yes**|
|Key|string|参数名称（与Value配合使用）|No|
|Value|string|参数值（与Key配合使用）|No|
|Name|string|配置文件的名字，不传时认为不修改名字，传了则不能为空|No|
|Description|string|配置文件的描述，不传时认为不修改|No|
|RegionFlag|bool|该配置文件是否是地域级别配置文件，默认是false|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateUDBParamGroup     
&Region=cn-bj2
&Zone=cn-bj2-04
&GroupId=2
&Key=back_log
&Value=2000
&Name=CJCMVDSu
&Description=WkHCyoXe
&RegionFlag=Wggcb
```

# Response Example
```
{
    "Action": "UpdateUDBParamGroupResponse", 
    "RetCode": 0
}
```

