# 修改GlobalSSH 源站信息 - ModifyGlobalSSHOriginInfo

## 简介

修改GlobalSSH 源站信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ModifyGlobalSSHOriginInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyGlobalSSHOriginInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID,如org-xxxx。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **InstanceType** | string | Free,Basic,Enterprise,Ultimate |**Yes**|
| **RsIP** | string | 被SSH访问的源站IP |**Yes**|
| **InstanceId** | string | 资源ID:ugaa-xxxxxxx |**Yes**|
| **Area** | string | 填写支持SSH访问IP的地区名称，如“洛杉矶”，“新加坡”，“香港”，“东京”，“华盛顿”，“法兰克福”。Area和AreaCode两者必填一个 |No|
| **AreaCode** | string | AreaCode, 区域航空港国际通用代码。Area和AreaCode两者必填一个 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyGlobalSSHOriginInfo
&ProjectId=bCQaoFxj
&Area=oXkuHWSL
&TargetIP=DauVqsLd
&Port=7
&AreaCode=AiGYGiKQ
&Remark=QrcYWenh
&ChargeType=Year
&Quantity=4
&InstanceType=nzlyAdYg
&BandwidthPackage=1
&ForwardRegion=bJWEfuKO
&CouponId=tmnYxCXf
&InstanceType=iaoHdBYS
&InstanceID=LnHoApfC
```

### 响应示例
    
```json
{
  "AcceleratingDomain": "tmZhZrTF",
  "Action": "ModifyGlobalSSHOriginInfoResponse",
  "InstanceId": "cRwAaxst",
  "Message": "WWWxsBVZ",
  "RetCode": 0
}
```





