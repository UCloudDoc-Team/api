# 重装容器-ReInstallContainer

重装容器

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ContainerId|string|容器ID|**Yes**|
|ImageUrl|string|容器镜像地址，如uhub.service.ucloud.cn/centos6-ssh:latest|**Yes**|
|Name|string|容器名|**Yes**|
|Hostname|string|容器的主机名，主机名只能支持小写字母数字和减号，最大长度64|No|
|Password|string|密码只能用于ucloud/*-ssh镜像|No|
|Usage|int|只能是1或3，1-默认，3-pod|No|
|CPU|float|CPU个数，默认0.1|No|
|Memory|int|内存大小：默认128M|No|
|Enviroment|string|环境变量：[key:val]|No|
|SvcName|string|服务名，Usage=3时必传|No|
|SvcPort|int|后端服务端口，Usage=3时必传|No|
|Volume|string|容器内需要持久化的目录|No|
|Privileged|bool|是否给容器超级权限|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ContainerSet|array|Container信息|No|

# Request Example
```
https://api.ucloud.cn/?Action=ReInstallContainer
&Region=cn-bj2
&ProjectId=org-xxx
&ContainerId=docker-xxx
&ImageUrl=uhub.service.ucloud.cn/ucloud/ubuntu-14.04-ssh:latest
&Name=Container
&CPU=0
&Memory=0
```

# Response Example
```
{
    "Action": "ReInstallContainerResponse", 
    "ContainerSet": [
        "docker-xxx"
    ], 
    "RetCode": 0
}
```

