# 修改云主机内部 IP 地址-ModifyUHostIP

修改云主机内网 IP 地址

!> 进行此操作前，请在主机内部修改完配置文件，并关闭您的主机。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写时为默认项目。请参考[GetProjectList接口](api/summary/get_project_list)|No|
|PresentIpAddress|string|需要修改为的 IP 地址。新的IP地址和旧IP地址必须属于统一子网，且和主机内部的配置文件一致。|**Yes**|
|UHostId|string|指定云主机 ID。|**Yes**|
|PreviousIpAddress|string|所需修改的原 IP 地址 ，当云主机只有一个IP地址时，此参数不必填写。|No|

?> 修改后的IP地址必须和原IP地址同vpc，同子网。

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|输出错误的信息|No|
|UHostId|string|目标云主机 ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyUHostIP
&Region=cn-bj2
&Zone=cn-bj2-04
&PresentIpAddress=192.168.0.77
&UHostId=uhost-xxxxx
```

# Response Example
```
{
    "Action": "ModifyUHostIPResponse", 
    "UHostId": "uhost-xxxxx", 
    "RetCode": 0
}
```

