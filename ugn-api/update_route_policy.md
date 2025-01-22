# 修改路由策略 - UpdateRoutePolicy

## 简介

修改路由策略






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateRoutePolicy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateRoutePolicy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **UGNID** | string | 云联网实例ID |**Yes**|
| **Policy.PolicyId** | string | 路由策略ID |**Yes**|
| **Policy.Name** | string | 策略名称，限定长度 255 |No|
| **Policy.Direction** | string | 策略方向，限定取值："In"/"Out" |No|
| **Policy.Priority** | int | 策略优先级，范围：[1,255]，数值越小优先级越大，同一方向，策略优先级不可重复 |No|
| **Policy.Action** | string | 策略执行动作，限定取值："Permit"/"Deny" |No|
| **Policy.RoutePriority** | int | 当执行动作为 "Permit" 时，给匹配中的路由设置路由优先级，范围：[1,255]，数值越小优先级越大 |No|
| **SrcRegions.N** | string | 路由策略需要匹配的路由的所在地域数组 |No|
| **SrcNetworkTypes.N** | string | 路由策略需要匹配的路由的网络实例类型数组，限定取值："VPC" |No|
| **SrcNetworks.N.NetworkId** | string | 路由策略需要匹配的路由的网络实例ID数组 |No|
| **Prefixes.N** | string | 路由策略需要匹配的路由的网络实例下的网段数组 |No|
| **DstNetworkTypes.N** | string | 路由策略需要作用的网络实例类型数组，限定取值："VPC" |No|
| **DstNetworks.N.NetworkId** | string | 路由策略需要作用的网络实例ID数组 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateRoutePolicy
&ProjectId=EQAZLuPL
&UGNID=SKPFqLiQ
&Policy.PolicyId=AVXBdPux
&Policy.Direction=ylmeXuIv
&Policy.Priority=2
&Policy.Action=uuvJNtOH
&Policy.RoutePriority=9
&Policy.SrcRegions.n=7
&Policy.SrcNetworkTypes.n=yuJrxWqH
&Policy.SrcNetworks.n.NetworkId=ZaNqcstG
&Policy.SrcNetworks.n.Prefixes.n=BNHNIAkv
&Policy.DstNetworkTypes.n=nYLLCpvL
&Policy.DstNetworks.n.NetworkId=FRfzTgwJ
&Policy.Name=KCQlOqzq
```

### 响应示例
    
```json
{
  "Action": "UpdateRoutePolicyResponse",
  "Policies": [
    {
      "Action": "AwZDVVAZ",
      "Direction": "aBjehwSB",
      "DstNetworkTypes": [
        "RAEkuDrc"
      ],
      "DstNetworks": [
        {
          "NetworkId": "BemGsZrk",
          "Prefixes": [
            "xuWLesLI"
          ]
        }
      ],
      "Enabled": false,
      "PolicyId": "CJnQwTDh",
      "Priority": 3,
      "Region": 3,
      "RoutePriority": 8,
      "SrcNetworkTypes": [
        "ySwFhOIV"
      ],
      "SrcNetworks": [
        {
          "NetworkId": "KZOyuKxH",
          "Prefixes": [
            "zAYqRNUG"
          ]
        }
      ],
      "SrcRegions": [
        5
      ]
    }
  ],
  "RetCode": 0
}
```





