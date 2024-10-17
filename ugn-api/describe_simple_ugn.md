# 获取简洁版UGN详情 - DescribeSimpleUGN

## 简介

获取简洁版UGN详情






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeSimpleUGN)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSimpleUGN`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **UGNID** | string | UGN ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGN** | [*UGN*](#UGN) |  |**Yes**|
| **Networks** | array[[*SimpleNetwork*](#SimpleNetwork)] |  |**Yes**|
| **BwPackages** | array[[*SimpleBwPackage*](#SimpleBwPackage)] |  |**Yes**|
| **Routes** | array[[*SimpleRoute*](#SimpleRoute)] |  |**Yes**|

#### 数据模型


#### UGN

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UGNID** | string | 云联网资源 ID |**Yes**|
| **Name** | string | 云联网名称 |**Yes**|
| **Remark** | string | 云联网备注 |**Yes**|
| **CreateTime** | int | 云联网创建时间 |**Yes**|
| **NetworkCount** | int | 关联网络实例数量 |**Yes**|
| **BwPackageCount** | int | 绑定带宽包数量 |**Yes**|

#### SimpleNetwork

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 网络实例所在地域 |**Yes**|
| **NetworkID** | string | 网络实例的ID，如 vnet-xxxxx |**Yes**|
| **Name** | string | 网络实例名称 |**Yes**|
| **Type** | string | 网络实例类型：VPC/HybridGW/... |**Yes**|
| **OrgName** | string | 网络实例所在项目名 |**Yes**|
| **RegionID** | int | 网络实例所在地域ID |No|
| **OrgID** | int | 网络实例所在项目的ID |No|
| **CreateTime** | int |  |No|

#### SimpleBwPackage

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PackageID** | string |  |**Yes**|
| **UGNID** | string |  |**Yes**|
| **PayMode** | string | 计费模式 FixedBw:固定带宽｜Peak95:经典95｜Max5:第五峰值｜Traffic:流量计费 |**Yes**|
| **RegionA** | string | 地域A名称 |**Yes**|
| **RegionB** | string | 地域B名称 |**Yes**|
| **BandWidth** | float | 带宽值 |**Yes**|
| **Qos** | string | 服务质量<br />Diamond:钻石｜Platinum:铂金｜Gold:黄金 |**Yes**|
| **Path** | string | 智能路径<br />Delay:最低时延｜IGP:普通线路｜TCO:最低成本 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **Name** | string |  |No|
| **Remark** | string |  |No|
| **ExpireTime** | int | 过期时间 |No|
| **ChangeStatus** | int | 带宽包切换状态 |No|
| **ChangeTime** | int | 带宽包切换时间 |No|
| **ChangePayMode** | string | 带宽包切换计费类型 |No|

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

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSimpleUGN
&ProjectId=GoyMEaqI
&UGNID=BqXFlXPM
```

### 响应示例
    
```json
{
  "Action": "DescribeSimpleUGNResponse",
  "BwPackages": [
    {
      "ChangePayMode": "pcnbFlpQ",
      "ChangeStatus": 6,
      "ChangeTime": 1,
      "CreateTime": 5,
      "ExpireTime": 9,
      "IsCrossBorder": true,
      "Message": "upqtoHLo",
      "Name": "BIueGIVJ",
      "PackageID": "vjpUMeWg",
      "Path": "TCO|IGP|Delay",
      "PayMode": "Free|SolidBw|Peak95|Max5|Traffic",
      "Qos": "金|银|铜",
      "RegionA": "dxBALSbx",
      "RegionABwMax": 8,
      "RegionABwMin": 5,
      "RegionB": "OTEAkkrX",
      "RegionBBwMax": 9,
      "RegionBBwMin": 6,
      "Remark": "xLwRqlaF",
      "UGNID": "IokLUMlQ"
    }
  ],
  "Message": "ekWmsxEt",
  "Networks": [
    {
      "NICs": [
        {
          "IP": "mDJBSJNd",
          "Mac": "vaxygoWB"
        }
      ]
    }
  ],
  "Policies": [
    "mgWCSWoN"
  ],
  "RetCode": 0,
  "Routes": [
    {
      "DstAddr": "MnPDhhax",
      "NexthopID": "TCwWNQyx",
      "NexthopRegion": "PzANTsVh",
      "NexthopRegionID": 1,
      "NexthopType": "NKCXpCxj",
      "Priority": 4
    }
  ],
  "UGN": {}
}
```





