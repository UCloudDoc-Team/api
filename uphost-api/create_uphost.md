# 创建物理机-CreatePHost

指定数据中心，根据资源使用量创建指定数量的UPHost物理云主机实例。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ImageId|string|镜像资源id,参见describephostimage|**Yes**|
|Password|string|密码|**Yes**|
|Type|string|物理机类型，默认为：db-2(数据库型32核)|No|
|Name|string|物理机名称，默认为phost|No|
|Remark|string|物理机备注，默认为空|No|
|Tag|string|业务组，默认为default|No|
|ChargeType|string|计费模式，枚举值为：year, 按年付费； month,按月付费；dynamic，按需付费，（需开启权限） trial, 试用（需开启权限）。默认为按月付费|No|
|Quantity|string|购买时长，默认为1，范围[1-10]|No|
|Count|int|购买数量，默认为1,范围[1-5]|No|
|SecurityGroupId|string|防火墙Id，默认：Web推荐防火墙。如何查询SecurityGroupId请参见 [DescribeSecurityGroup](api/unet-api/describe_security_group)|No|
|Raid|string|Raid配置，默认Raid10|No|
|VPCId|string|VPC ID，不填为默认，VPC2.0下需要填写此字段。|No|
|SubnetId|string|子网ID，不填为默认，VPC2.0下需要填写此字段。|No|
|Cluster|string|网络环境，可选千兆：1G ，万兆：10G， 默人1G|No|
|CouponId|string|代金券|No|

```
密码需要通过base64进行编码

# echo -n password1 | base
cGFzc3dvcmQx
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PHostId|array|PHost的资源ID数组|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreatePHost
&Region=hk
&Zone=hk-01
&ProjectId=org-xxx
&ImageId=pimg-xxx
&Password=xxx
&Name=123
&ChargeType=Month
&Quantity=10
&Count=1
```

# Response Example
```
{
    "Action": "CreatePHostResponse", 
    "PHostId": [
        "upm-xxx"
    ], 
    "RetCode": 0
}
```

