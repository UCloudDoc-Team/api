# 创建容器实例-CreateContainerInstance

创建容器实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ClusterId|string|集群ID|**Yes**|
|Name|string|容器名字|**Yes**|
|ImageUrl|string|镜像名，格式：url/image:tag如uhub.service.ucloud.cn/centos6-ssh:latest|**Yes**|
|NodeId|string|节点ID，默认随机选择集群中一个节点|No|
|CPU|float|CPU个数，默认0.1，精度0.1|No|
|Memory|float|内存M：默认128M，精度1|No|
|Enviroment|string|环境变量：[key:val]|No|
|AddHost|string|对应—add-host 参数，每个用逗号隔开，字符串格式：n1:ip1,n2:ip2,n3:ip3|No|
|Cmd|string|容器启动命令|No|
|Volume|string|容器内需要挂载的目录|No|
|Count|int|实例个数，默认1，最大100|No|
|Password|string|ucloud镜像（ImageType=0）且以-ssh结尾时，必须输入密码（默认密码为节点ID）|No|
|Hostname|string|容器内的hostname（主机名）|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ContainerSet|array|容器ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateContainerInstance
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=org-xxx
&ClusterId=cluster-xxx
&Name=Container
&ImageUrl=uhub.service.ucloud.cn/ucloud/centos6-ssh:latest
&NodeId=dnode-xxx
&CPU=0
&Memory=0
&Volume=/data
```

# Response Example
```
{
    "Action": "CreateContainerInstanceResponse", 
    "ContainerSet": [
        "docker-xxx"
    ], 
    "RetCode": 0
}
```

