# 修改云主机内部 IP 地址 - ModifyUHostIP

## 简介

修改云主机内网 IP 地址

?> 修改后的IP地址必须和原IP地址同vpc，同子网。

!> 进行此操作前，请在主机内部修改完配置文件，并关闭您的主机。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ModifyUHostIP)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyUHostIP`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写时为默认项目。请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **PresentIpAddress** | string | 需要修改为的 IP 地址。新的IP地址和旧IP地址必须属于统一子网，且和主机内部的配置文件一致。 |**Yes**|
| **UHostId** | string | 指定云主机 ID。 |**Yes**|
| **PreviousIpAddress** | string | 所需修改的原 IP 地址 ，当云主机只有一个IP地址时，此参数不必填写。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UHostId** | string | 目标云主机 ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyUHostIP
&Region=cn-bj2
&Zone=cn-bj2-04
&PresentIpAddress=192.168.0.77
&UHostId=uhost-xxxxx
```

### 响应示例
    
```json
{
  "Action": "ModifyUHostIPResponse",
  "RetCode": 0,
  "UHostId": "uhost-xxxxx"
}
```





