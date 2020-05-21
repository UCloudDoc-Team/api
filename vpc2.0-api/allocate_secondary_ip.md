# 分配ip - AllocateSecondaryIp

## 简介

分配ip（用于uk8s使用）






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AllocateSecondaryIp)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AllocateSecondaryIp`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **Mac** | string | 节点mac |**Yes**|
| **ObjectId** | string | 资源Id |**Yes**|
| **SubnetId** | string | 子网Id（若未指定，则根据zone获取默认子网进行创建） |No|
| **VPCId** | string | vpcId |No|
| **Ip** | string | 指定Ip分配 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **IpInfo** | [*IpInfo*](#IpInfo) |  |**Yes**|

#### 数据模型


#### IpInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Ip** | string |  |No|
| **Mask** | string |  |No|
| **Gateway** | string |  |No|
| **Mac** | string |  |No|
| **SubnetId** | string |  |No|
| **VPCId** | string |  |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AllocateSecondaryIp
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=rvlPceNj
&ObjectId=ttFJuSUK
&Mac=hYZEoFAm
&SubnetId=ZFUgcsnL
```

### 响应示例
    
```json
{
  "Action": "AllocateSecondaryIpResponse",
  "IpInfo": {
    "AccountId": 0,
    "AzId": 0,
    "Gateway": "XXX.XXX.XX.X",
    "Ip": "XX.XX.XX.XXX",
    "IpType": 0,
    "Mac": "XX:XX:XX:XX:XX:XX",
    "Mask": "255.255.XXX.X",
    "ObjectId": "",
    "OperatorId": 0,
    "OtherIp": "",
    "OtherIpMask": "",
    "PipId": "",
    "SubnetworkId": "subnet-XXXX",
    "SubnetworkType": 0,
    "VIP": null,
    "VPCId": "uvnet-XXXX",
    "ZoneId": 0
  },
  "RetCode": 0
}
```





