# 创建服务-CreateSVC

创建服务

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ClusterId|string|集群ID|**Yes**|
|SvcName|string|服务名，用于匹配后端，最大长度128字符，只能包括小写字母、数字和点号|**Yes**|
|PortMap.n|string|格式PORT1:PORT2 用于指定端口映射|**Yes**|
|CPU|float|CPU个数|**Yes**|
|Memory|int|内存MB|**Yes**|
|NodeId|string|节点ID|No|
|Count|int|数量|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ProxyIds|array|返回ID列表|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateSVC
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-xxx
&ClusterId=cluster-xxx
&SvcName=service1
&CPU=1
&Memory=128
&NodeId=dnode-xxx
&PortMap.0=80:80
```

# Response Example
```
{
    "Action": "CreateSVCResponse", 
    "RetCode": 0, 
    "ProxyIds": [
        "docker-xxx"
    ]
}
```

