# 创建Pod-CreatePod

创建Pod

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ImageUrl|string|镜像完整路径|**Yes**|
|ClusterId|string|集群ID|**Yes**|
|Name|string|容器名字|**Yes**|
|SvcName|string|服务名字，和SVC的服务名字做匹配。Usage=3时必填，只能是小写字母数字加上点号和减号的组合，且不能以标点开始，最大长度128.|**Yes**|
|NodeId|string|节点ID，默认随机选择集群中一个节点|No|
|CPU|float|CPU个数，默认0.1，精度0.1|No|
|Memory|float|内存M：默认128M，精度1|No|
|Enviroment|string|环境变量：[key:val]|No|
|AddHost|string|对应—add-host 参数，每对name:ip用逗号隔开，字符串格式：n1:ip1,n2:ip2,n3:ip3|No|
|Cmd|string|容器启动命令|No|
|Volume|string|容器内需要挂载的目录|No|
|Count|int|实例个数，默认1，最大100|No|
|Password|string|ucloud镜像（ImageType=0）且以-ssh结尾时，必须输入密码（默认密码为节点ID）|No|
|Hostname|string|容器内的hostname（主机名）|No|
|SvcPort|int|服务通过该端口访问后端服务，因此和SVC的端口无关。Usage=3时必填|No|
|OtherOptions|string|其他选项，容器命令行中的其他高级选项|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PodIds|array|容器ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreatePod
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-xxx
&ImageUrl=uhub.service.ucloud.cn/ucloud/centos6-ssh:latest
&ClusterId=cluster-xxx
&Name=service22-pod
&SvcName=service22
&CPU=0
&Memory=0
&Count=1
```

# Response Example
```
{
    "Action": "CreatePodResponse", 
    "PodIds": [
        "docker-xxx"
    ], 
    "RetCode": 0
}
```

