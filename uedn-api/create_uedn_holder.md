# 创建容器组 - CreateUEdnHolder

## 简介

创建容器组









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUEdnHolder`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **IdcId** | string | 机房id |**Yes**|
| **CpuCore** | float | 容器组Cpu总核数 |**Yes**|
| **MemSize** | int | 容器组总内存，单位MB |**Yes**|
| **SubnetId** | string | 子网ID |**Yes**|
| **Name** | string | 容器组名称（默认default） |No|
| **ProductType** | string | 机型（normal-标准型，hf-高性能型，默认normal） |No|
| **RestartStrategy** | int | 重启策略（0总是，1失败是，2永不，默认0） |No|
| **ElasticIp** | string | 绑定外网ip（yes-绑定，no-不绑定，默认no） |No|
| **Bandwidth** | int | 外网绑定的带宽（单位M，默认0，只有当ElasticIp为yes时，默认1） |No|
| **FirewallId** | string | 防火墙ID |No|
| **ChargeType** | int | 付费方式（2按月、3按年。默认2，默认月付） |No|
| **ChargeQuantity** | int | 月数或者年数（默认值：1，当为按月计费时，0表示计费到月底，默认值为0） |No|
| **Pack.N.Name** | string | 容器名称 |No|
| **Pack.N.CpuCore** | float | 容器Cpu核数 |No|
| **Pack.N.MemSize** | int | 容器内存，单位MB |No|
| **Pack.N.ImageName** | string | 容器镜像名称 |No|
| **Pack.N.WorkDir** | string | 容器工作目录 |No|
| **Pack.N.Cmd** | string | 开启容器的命令 |No|
| **Pack.N.Args** | string | 容器参数（多个用；隔开） |No|
| **Pack.N.Environment** | string | 容器环境变量（多个用；隔开,如：key1:value1;key2:value2） |No|
| **Image.N.Message** | string | 镜像用户名和密码（如镜像名：密码） |No|
| **Image.N.StoreAddress** | string | 镜像仓库地址 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ResourceId** | string | 容器组资源id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUEdnHolder
&ProjectId=lZUdEfYo
&IdcId=ydmvyMLJ
&CpuCore=4.91848
&MemSize=5
&Name=gZtyGNVi
&ProductType=qwPtlLpZ
&RestartStrategy=2
&ElasticIp=RzadiHut
&Bandwidth=9
&SubnetId=vrpJwDWi
&FirewallId=uivCgcVE
&ChargeType=8
&ChargeQuantity=5
&Pack.n.Name=aQxyTkDy
&Pack.n.CpuCore=9.89585
&Pack.n.MemSize=1
&Pack.n.ImageName=TlzQlVYB
&Pack.n.WorkDir=ZUGtdizY
&Pack.n.Cmd=eGspogeD
&Pack.n.Args=BezUlgYY
&Pack.n.Environment=QwnBGWkn
&Image.n.Message=LawPEWaY
&Image.n.StoreAddress=RjdIMkCN
```

### 响应示例
    
```json
{
  "Action": "CreateUEdnHolderResponse",
  "ResourceId": "MneWaCIH",
  "RetCode": 0
}
```





