# 获取实例数据库连接信息 - GetUDBAccessInfo

## 简介

查询 UDB 实例的内网与外网访问信息，包含外网地址端口、带宽、白名单，以及内网 VPC、子网、内网 IP、内网域名与端口1






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUDBAccessInfo)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUDBAccessInfo`                        | **Yes** |
| **PublicKey**  | string  | AccessKey ID，在 [控制台](https://console.ucloud.cn/uaccount/api_manage) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **DBId** | string | 实例ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ExternalInfo** | array[[*ExternalInfo*](#ExternalInfo)] | 实例外网访问信息，含状态、地址、端口、带宽与白名单 |**Yes**|
| **PrivateInfo** | array[[*PrivateInfo*](#PrivateInfo)] | 实例内网访问信息，含 VPC、子网、内网 IP、内网域名与端口 |**Yes**|

#### 数据模型


#### ExternalInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Status** | string | 外网访问状态，字符串枚举，取值见下表 |No|
| **ExternalAddress** | string | 外网访问地址；未开通外网访问时为空字符串 |No|
| **ExternalPort** | int | 外网访问端口；未开通时为 0 |No|
| **Bindwidth** | int | 外网带宽，单位 Mbps，取自 EIP 带宽；无 EIP 时为 0 |No|
| **WhiteList** | string | 外网访问白名单，多个 IP 以逗号分隔，取自 NLB 白名单 |No|
| **Support** | int | 实例是否支持外网访问能力：1 支持；当前实现恒返回 1 |No|

#### PrivateInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VPCId** | string | 实例内网所在的 VPC ID |No|
| **SubnetId** | string | 实例内网所在的子网 ID |No|
| **PrivateIP** | string | 实例内网服务地址（VIP） |No|
| **PrivateDomain** | string | 实例的内网域名；未开通内网域名时为空字符串 |No|
| **PrivatePort** | int | 内网域名状态，字符串枚举，取值与 Status 同源；未开通内网域名时返回<br />NetworkConnectionDisabled |No|
| **PrivateDomainStatus** | string | 实例内网服务端口 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUDBAccessInfo
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=jfYVSckZ
&DBId=nbQrcarW
```

### 响应示例
    
```json
{
  "Action": "GetUDBAccessInfoResponse",
  "ExternalInfo": [
    {
      "Bindwidth": 3,
      "ExternalAddress": "RCdpDkLM",
      "ExternalPort": 3,
      "Status": "iQFLtuBU",
      "Support": 5,
      "WhiteList": "zOsIWYbP"
    }
  ],
  "Message": "EKNTQNRV",
  "PrivateInfo": [
    {
      "PrivateDomain": "AXTyTYtL",
      "PrivateIP": "xijCIWfz",
      "PrivatePort": 4,
      "SubnetId": "vEhrqbTk",
      "VPCId": "mDliIGzu"
    }
  ],
  "RetCode": 0
}
```





