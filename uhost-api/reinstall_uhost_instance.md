# 重装系统 - ReinstallUHostInstance

## 简介

重新安装指定UHost实例的操作系统



!> 1.请确认在重新安装之前，该实例已被关闭； 2.将原系统重装为不同类型的系统时(Linux-&gt;Windows)，不可选择保留数据盘； 3.重装不同版本的系统时(CentOS6-&gt;CentOS7)，若选择保留数据盘，请注意数据盘的文件系统格式；


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ReinstallUHostInstance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


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
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UHostId** | string | UHost实例资源ID 参见 [DescribeUHostInstance](api/uhost-api/describe_uhost_instance) |**Yes**|
| **Password** | string | 如果重装UHost实例时LoginMode为Password，则必须填写，如果LoginMode为KeyPair，不需要填写 （密码格式使用BASE64编码；举例如下：# echo -n Password1 \| base64UGFzc3dvcmQx。） |No|
| **ImageId** | string | 镜像Id，默认使用原镜像 参见 [DescribeImage](api/uhost-api/describe_image) |No|
| **ReserveDisk** | string | 是否保留数据盘，保留：Yes，不保留：No， 默认：Yes；如果是从Windows重装为Linux或反之，则无法保留数据盘（该参数目前仅对本地数据盘起作用） |No|
| **BootDiskSpace** | int | 系统盘大小。 单位：GB， 范围[20,100]。 |No|
| **UserData** | string | cloudinit初始化使用。注意：1、总数据量大小不超多16K 2、使用base64编码 |No|
| **AutoDataDiskInit** | string | 数据盘是否需要自动分区挂载。当镜像支持Cloud-init Feature时可填写此字段。取值“On”（默认值）， “Off” |No|
| **LoginMode** | string | 主机登陆模式。密码（默认选项）: Password，密钥 KeyPair，自制镜像密码: ImagePasswd。 |No|
| **KeyPairId** | string | KeypairId 密钥对ID，LoginMode为KeyPair时此项必须。 |No|
| **HostName** | string | 操作系统主机名 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UHostId** | string | UHost实例资源ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ReinstallUHostInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&UHostId=uhost-xxx
&Password=xxx
&BootDiskSpace=6
&UserData=TdFuRmBV
&AutoDataDiskInit=LpCzTmbU
&LoginMode=yOknHzpM
&KeyPairId=KfXBMRLJ
&KeyPairId=qqNpnbqV
&HostName=LQWDgkPa
```

### 响应示例
    
```json
{
  "Action": "ReinstallUHostInstanceResponse",
  "RetCode": 0,
  "UHostId": "uhost-xxx"
}
```





