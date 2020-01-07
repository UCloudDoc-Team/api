# 创建节点-CreateUvodnNode

创建节点v2.0

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|IdcId|string|机房id|**Yes**|
|CpuCore|int|cpu核心数|**Yes**|
|MemSize|int|内存大小，单位GB|**Yes**|
|DiskSize|int|数据盘大小，单位GB|**Yes**|
|ImageId|string|镜像ID|**Yes**|
|NetLimit|int|节点带宽限制，单位Mbs|**Yes**|
|NodeName|string|节点名称|No|
|SysDiskSize|int|系统盘大小，单位GB， 默认20GB|No|
|AccountName|string|账户名，默认root|No|
|PassWord|string|密码|No|
|NodeCount|int|创建节点数量，默认1|No|
|ChargeType|int|付费方式，2按月，3按年，默认2|No|
|ChargeQuantity|int|月数或者年数，0计费到月底， 默认0|No|
|SubnetId|string|子网ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|NodeList|array|节点id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUvodnNode
&ProjectId=org-xxx
&IdcId=uedn-idc-xxx
&CpuCore=1
&MemSize=2
&ImageId=uedn-image-xxx
&NetLimit=2
&NodeName=test
&SysDiskSize=20
&AccountName=root
&PassWord=xxx
&NodeCount=1
&ChargeType=2
&ChargeQuantity=1
```

# Response Example
```
{
    "Action": "CreateUvodnNodeResponse", 
    "NodeList": [
        {
            "NodeId": "uedn-node-xxx"
        }
    ], 
    "RetCode": 0
}
```

