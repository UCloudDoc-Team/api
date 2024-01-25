# 修改主机规格 - ResizeUHostInstance

## 简介

修改指定UHost实例的资源配置，如CPU核心数，内存容量大小，网络增强等。可选配置范围请参考[云主机机型说明](api/uhost-api/uhost_type)。

?> 若需调整磁盘大小，请调用ResizeAttachedDisk。

!> 1.修改配置前，请确认该实例已经被关闭。<br />2.修改磁盘空间大小后，请在启动后按照说明，进入操作系统进行操作。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ResizeUHostInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ResizeUHostInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UHostId** | string | UHost实例ID 参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance) |**Yes**|
| **CPU** | int | 虚拟CPU核数。可选参数：1-240（可选范围与UHostType相关）。默认值为当前实例的CPU核数 |No|
| **Memory** | int | 内存大小。单位：MB。范围 ：[1024, 1966080]，取值为1024的倍数（可选范围与UHostType相关）。默认值为当前实例的内存大小。 |No|
| **GPU** | int | GPU卡核心数。仅GPU机型支持此字段（可选范围与MachineType+GpuType相关） |No|
| **NetCapValue** | int | 网卡升降级（1，表示升级，2表示降级，0表示不变） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UHostId** | string | UHost实例ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ResizeUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&UHostId=uhost-xxx
&CPU=4
&Memory=2048
&GPU=5
&GPU=6
```

### 响应示例
    
```json
{
  "Action": "ResizeUHostInstanceResponse",
  "RetCode": 0,
  "UHostId": "uhost-xxx"
}
```





