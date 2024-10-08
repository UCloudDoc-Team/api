# 重置主机密码 - ResetUHostInstancePassword

## 简介

重置UHost实例的管理员密码。



!> 该操作需要UHost实例处于关闭状态。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ResetUHostInstancePassword)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ResetUHostInstancePassword`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UHostId** | string | UHost实例ID |**Yes**|
| **Password** | string | UHost新密码（密码格式使用BASE64编码） |No|
| **LoginMode** | string | 主机登陆模式。密码（默认选项）: Password，密钥 KeyPair。 |No|
| **KeyPairId** | string | KeypairId 密钥对ID，LoginMode为KeyPair时此项必须。 |No|
| **AutoStart** | boolean | 修改密码结束后是否立即开机，默认为false， 如果设置为true，则修改密码成功后立即开机； 抢占式和后付费云主机暂不支持当前功能； |No|

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
https://api.ucloud.cn/?Action=ResetUHostInstancePassword
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&UHostId=uhost-xxx
&Password=xxx

&LoginMode=EDgIxjbH
&KeyPairId=hJOtYxkc
&AutoStart=true
```

### 响应示例
    
```json
{
  "Action": "ResetUHostInstancePasswordResponse",
  "RetCode": 0,
  "UHostId": "uhost-xxx"
}
```





