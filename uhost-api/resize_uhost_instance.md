# 修改主机配置 - ResizeUHostInstance

## 简介

修改指定UHost实例的资源配置，如CPU核心数，内存容量大小，磁盘空间大小,网络增强等。

?> 须按照控制台标准机型配置创建主机（例如：无法创建16核1G的非标准机型）。详情请参考控制台。

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
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **UHostId** | string | UHost实例ID 参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance) |**Yes**|
| **CPU** | int | 虚拟CPU核数，单位：个，范围：[1,16]，最小值为1，其他值是2的倍数，默认值为当前实例的CPU核数（*windows CPU>=2） |No|
| **Memory** | int | 内存大小，单位：MB，范围[2048,65536]，步长：2048，默认值为当前实例的内存大小（BGP-C数据中心最小支持1024，限Linux系统） |No|
| **DiskSpace** | int | 数据盘大小，单位：GB，范围[10,1000]； SSD机型，单位：GB，范围[100,500]；步长：10，默认值为当前实例的数据盘大小，数据盘不支持缩容，因此不允许输入比当前实例数据盘大小的值 |No|
| **BootDiskSpace** | int | 系统盘大小，单位：GB，范围[20,100]，步长：10，系统盘不支持缩容，因此不允许输入比当前实例系统盘小的值 |No|
| **NetCapValue** | int | 网卡升降级（1，表示升级，2表示降级，0表示不变） |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UhostId** | string | UHost实例ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ResizeUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostId=uhost-qs20fr
&CPU=4
```

### 响应示例
    
```json
{
  "Action": "ResizeUHostInstanceResponse",
  "RetCode": 0
}
```





