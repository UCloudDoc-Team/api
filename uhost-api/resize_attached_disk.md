# 修改挂载的磁盘大小 - ResizeAttachedDisk

## 简介

修改挂载的磁盘大小，包含系统盘和数据盘



!> 1.修改配置前，请确认该实例已经被关闭。<br />2.修改磁盘空间大小后，请在启动后按照说明，进入操作系统进行操作。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ResizeAttachedDisk)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ResizeAttachedDisk`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **UHostId** | string | UHost实例ID。 参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance)。 |**Yes**|
| **DiskSpace** | int | 磁盘大小，单位GB，步长为10。取值范围需大于当前磁盘大小，最大值请参考[磁盘类型](api/uhost-api/disk_type)。 |**Yes**|
| **DiskId** | string | 磁盘ID。参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance)返回值中的DiskSet。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DiskId** | string | 改配成功的磁盘id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ResizeAttachedDisk
&Region=cn-sh2
&Zone=cn-sh2-02
&UHostId=uhost-qfbc2i
&DiskId=bs-w5oyip
&DiskSpace=40
```

### 响应示例
    
```json
{
  "Action": "ResizeAttachedDiskResponse",
  "DiskId": "bs-w5oyip",
  "RetCode": 0
}
```





