# 更新VPC IPv6网段 - UpdateVPCIPv6

## 简介

更新VPC IPv6网段






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateVPCIPv6)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateVPCIPv6`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **VPCId** | string | VPC资源ID |**Yes**|
| **IPv6NetworkConfig.N.IPv6Network** | string | 需要保留的所有网段 |**Yes**|
| **IPv6NetworkConfig.N.OperatorName** | string | 网段对应的运营商类型 |**Yes**|
| **IPv6NetworkConfig.N.Type** | string | 网段分类：Default--默认网段、Custom--客户自带网段 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateVPCIPv6
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=kFZhlDoM
&VPCId=FScUAYno
&IPv6NetworkConfig.n=XIiWtttS
&IPv6NetworkConfig.N.OperatorName=txyNXofZ
&IPv6NetworkConfig.N.Type=LPAwVRTY
```

### 响应示例
    
```json
{
  "Action": "UpdateVPCIPv6Response",
  "Message": "yChQeNNY",
  "RetCode": 0
}
```





