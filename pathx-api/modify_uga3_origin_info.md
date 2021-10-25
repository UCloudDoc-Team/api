# 修改统一接入加速配置源站信息 - ModifyUGA3OriginInfo

## 简介

Domain， IPList注意：修改Domain或IPList时， 请确保源站服务端口已经开启且外网防火墙允许pathx出口ip访问。






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ModifyUGA3OriginInfo)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyUGA3OriginInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **InstanceId** | string | 加速配置实例ID，格式uga3-xxxx。 |**Yes**|
| **OriginDomain** | string | 加速源域名，仅支持1个域名。修改源站时 OriginIPList和OriginDomain至少填一个。OriginIPList和OriginDomain都填时 以Domain为准,如果两个都不填，不修改 |**Yes**|
| **OriginIPList** | string | ，加速源IP，多个IP用英文半角逗号(,)隔开。修改源站时 ，OriginIPList和OriginDomain至少填一个。OriginIPList和OriginDomain都填时 以OriginDomain为准。如果两个都不填，不修改 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyUGA3OriginInfo
&ProjectId=zBCRVsxO
&InstanceId=rmiOTiCA
&Domain=EGlsGjiZ
&Name=cJraflhd
&IPList=uTrPucJs
&Remark=UEEUHpMs
&Bandwidth=NxjXjvzm
&AreaCode=bwEPFNlh
&Area=dqeuImPC
&CouponId=nVdEDSME
```

### 响应示例
    
```json
{
  "Action": "ModifyUGA3OriginInfoResponse",
  "Message": "cfZKYCFR",
  "RetCode": 0
}
```





