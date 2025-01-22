# 启用\停用路由策略 - EnableRoutePolicy

## 简介

启用<br />停用路由策略






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=EnableRoutePolicy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `EnableRoutePolicy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **UGNID** | string | 云联网实例ID |**Yes**|
| **PolicyId** | string | 路由策略ID |**Yes**|
| **Enable** | boolean | 是否启用 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=EnableRoutePolicy
&ProjectId=DGXEDfus
&UGNID=zcCwkpLm
&PolicyId=QgZotSrl
&Enable=false
```

### 响应示例
    
```json
{
  "Action": "EnableRoutePolicyResponse",
  "Policies": [
    {
      "Action": "HSBLxvGJ",
      "Direction": "kHYCHrxu",
      "DstNetworkTypes": [
        "RKzczRUR"
      ],
      "DstNetworks": [
        {
          "NetworkId": "znsPaZCE",
          "Prefixes": [
            "XIqfpOIR"
          ]
        }
      ],
      "Enabled": false,
      "PolicyId": "ncgcLNwU",
      "Priority": 3,
      "Region": 1,
      "RoutePriority": 4,
      "SrcNetworkTypes": [
        "bPBLKGzS"
      ],
      "SrcNetworks": [
        {
          "NetworkId": "IeQJkOlB",
          "Prefixes": [
            "KHASYtGK"
          ]
        }
      ],
      "SrcRegions": [
        7
      ]
    }
  ],
  "RetCode": 0
}
```





