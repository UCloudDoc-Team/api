# 重装系统 - ReinstallUHostInstance

## 简介

重新安装指定UHost实例的操作系统



!> 1.请确认在重新安装之前，该实例已被关闭； 2.请确认该实例未挂载UDisk； 3.将原系统重装为不同类型的系统时(Linux-&gt;Windows)，不可选择保留数据盘； 4.重装不同版本的系统时(CentOS6-&gt;CentOS7)，若选择保留数据盘，请注意数据盘的文件系统格式； 5.若主机CPU低于2核，不可重装为Windows系统。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ReinstallUHostInstance)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ReinstallUHostInstance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **UHostId** | string | UHost实例资源ID 参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance) |**Yes**|
| **Password** | string | 如果创建UHost实例时LoginMode为Password，则必须填写，如果LoginMode为KeyPair，不需要填写 （密码格式使用BASE64编码；LoginMode不可变更） |No|
| **ImageId** | string | 镜像Id，默认使用原镜像 参见 [DescribeImage](api/uhost-api/describe_image) |No|
| **ReserveDisk** | string | 是否保留数据盘，保留：Yes，不报留：No， 默认：Yes |No|
| **ResourceType** | int | 云灾备指明191 |No|
| **DNSServers.N** | string | 针对非私有子网主机，可自定义DNS。n可为0-2 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UhostId** | string | UHost实例资源ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ReinstallUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostId=uhost-qs20fr
&Password=UCloud123
```

### 响应示例
    
```json
{
  "Action": "ReinstallUHostInstanceResponse",
  "RetCode": 0,
  "UHostId": "uhost-qs20fr"
}
```





