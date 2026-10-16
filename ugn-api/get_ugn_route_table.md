# 获取云联网路由表 - GetUGNRouteTable

## 简介

获取云联网路由表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUGNRouteTable)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUGNRouteTable`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **UGNID** | string | 云联网实例ID |**Yes**|
| **Type** | string | 路由表类型，分为初始路由表、中阶路由表以及最终路由表，限定取值："Origin"/"Middle"/"Final" |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGNID** | string | 云联网实例ID |**Yes**|
| **Routes** | array[[*SimpleRoute*](#SimpleRoute)] | 路由表，"Origin"/"Middle" 用这个 |**Yes**|
| **VRoutes** | array[[*VRoute*](#VRoute)] | 网络实例对应的路由表，"Final" 用这个 |**Yes**|

#### 数据模型


#### SimpleRoute

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DstAddr** | string | 目的网段 |No|
| **NextHopID** | string | 下一跳网络实例 ID |No|
| **NextHopType** | string | 下一跳网络实例类型 |No|
| **NextHopRegion** | string | 下一跳网络实例所属地域 |No|
| **NextHopRegionID** | int | 下一跳网络实例所属地域 id |No|
| **Priority** | int | 路由优先级 |No|
| **Deny** | boolean | true: 由于命中路由策略而失效 |No|
| **Restrict** | boolean | true: 由于优先级比其他前缀相同的路由低而失效 |No|
| **Conflict** | boolean | true: 由于优先级相同但插入数据库的时间比其他前缀相同的路由晚而失效 |No|
| **InPolicyId** | string | 匹配中的入向路由策略id |No|
| **InPolicyName** | string | 匹配中的入向路由策略名称 |No|
| **OutPolicyId** | string | 匹配中的出向路由策略id |No|
| **OutPolicyName** | string | 匹配中的出向路由策略名称 |No|

#### VRoute

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NetworkId** | string | 网络实例ID |No|
| **Routes** | array[[*SimpleRoute*](#SimpleRoute)] | 该网络实例对应的路由 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUGNRouteTable
&ProjectId=QCvgkWeh
&UGNID=VwptbMxl
&Type=YlkaMOMa
```

### 响应示例
    
```json
{
  "Action": "GetUGNRouteTableResponse",
  "RetCode": 0,
  "Routes": [
    {
      "DstAddr": "fAHJcMtE",
      "NexthopID": "vZDcdnBj",
      "NexthopRegion": "dgMYWzEd",
      "NexthopRegionID": 1,
      "NexthopType": "gGkNeCqn",
      "Priority": 2
    }
  ],
  "UGNID": "FAQELVHF",
  "VRoutes": "BPilasKo"
}
```





