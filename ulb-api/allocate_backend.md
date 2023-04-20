# 添加后端实例 - AllocateBackend

## 简介

添加ULB后端资源实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AllocateBackend)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AllocateBackend`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ULBId** | string | 负载均衡实例的ID |**Yes**|
| **VServerId** | string | VServer实例的ID |**Yes**|
| **ResourceType** | string | 所添加的后端资源的类型，枚举值：UHost -> 云主机；UNI -> 虚拟网卡；UPM -> 物理云主机； UDHost -> 私有专区主机；UDocker -> 容器；UHybrid->混合云主机；CUBE->Cube，USDP->智能大数据平台， IP->IP类型；默认值为UHost。报文转发模式不支持UDocker、UHybrid、CUBE、IP |**Yes**|
| **ResourceId** | string | 所添加的后端资源的资源ID |**Yes**|
| **ResourceIP** | string | 所添加的后端服务器的资源实例IP，当ResourceType 为 UHybrid 或 IP时有效，且必填 |No|
| **VPCId** | string | 所添加的后端服务器所在的vpc，当ResourceType 为 UHybrid 或 IP 时有效，且必填 |No|
| **SubnetId** | string | 所添加的后端服务器所在的子网，当ResourceType 为 UHybrid 或 IP 时有效，且必填 |No|
| **Port** | int | 所添加的后端资源服务端口，取值范围[1-65535]，默认80 |No|
| **Weight** | int | 所添加的后端RS权重（在加权轮询算法下有效），取值范围[1-100]，默认为1 |No|
| **Enabled** | int | 后端实例状态开关，枚举值： 1：启用； 0：禁用 默认为启用 |No|
| **IsBackup** | int | rs是否为backup，默认为0<br />0：普通rs<br />1：backup的rs |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BackendId** | string | 所添加的后端资源在ULB中的对象ID，（为ULB系统中使用，与资源自身ID无关），可用于 UpdateBackendAttribute/UpdateBackendAttributeBatch/ReleaseBackend |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AllocateBackend
&Region=cn-bj2
&ProjectId=project-XXXXX
&ULBId=ulb-XXXXX
&VServerId=vserver-XXXXX
&ResourceType=UHost
&ResourceId=uhost-XXXX 
&Port=80
&Enabled=1
&Weight=4
&IsBackup=4
&ResourceIP=ELVhVVux
&VPCId=qFbjvNJn
&SubnetId=DKBOyKER
```

### 响应示例
    
```json
{
  "Action": "AllocateBackendResponse",
  "BackendId": "backend-XXXXX",
  "RetCode": 0
}
```





