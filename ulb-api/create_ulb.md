# 创建负载均衡-CreateULB

创建负载均衡实例，可以选择内网或者外网

```
OuterMode 与 InnerMode 同时传 Yes 时，以 OuterMode 为准
当传了 InnerMode: Yes 之后，需要传一个 SubnetId 来表示用户选择了哪个子网
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|ULBName|string|负载均衡的名字，默认值为“ULB”|No|
|Tag|string|业务组|No|
|Remark|string|备注|No|
|OuterMode|string|创建的ULB是否为外网模式，默认即为外网模式|No|
|InnerMode|string|创建的ULB是否为内网模式|No|
|PrivateIp|string|创建内网ULB时指定内网IP。若不传值，则随机分配当前子网下的IP（暂时不对外开放，创建外网ULB该字段会忽略）|No|
|ChargeType|string|付费方式|No|
|VPCId|string|ULB所在的VPC的ID, 如果不传则使用默认的VPC|No|
|SubnetId|string|内网ULB 所属的子网ID，如果不传则使用默认的子网|No|
|BusinessId|string|ULB 所属的业务组ID，如果不传则使用默认的业务组|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ULBId|string|负载均衡实例的Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateULB
&Region=cn-bj2
&ProjectId=project-XXXXX
&ULBName=test
&OuterMode=Yes
&ChargeType=Month
&VPCId=vnet-XXXXX
&SubnetId=subnet-XXXXX
&Tag=test

```

# Response Example
```
{
    "Action": "CreateULBResponse", 
    "ULBId": "ulb-XXXXX", 
    "RetCode": 0
}
```

