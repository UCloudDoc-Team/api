# 节点重装系统-ReinstallUvodnNode

节点重装系统

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|NodeId|string|节点ID|**Yes**|
|ImageId|string|镜像ID|**Yes**|
|KeepData|int|是否保留数据盘数据， 0-不保留，1-保留，默认为1|No|
|Password|string|节点密码|No|
|SysDiskSize|int|系统盘大小，单位GB|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ReinstallUvodnNode
&ProjectId=org-xxx
&NodeId=uedn-node-xxx
&ImageId=uedn-image-xxx
&KeepData=1
&Password=xxx
&SysDiskSize=20
```

# Response Example
```
{
    "Action": "ReinstallUvodnNodeResponse", 
    "RetCode": 0
}
```

