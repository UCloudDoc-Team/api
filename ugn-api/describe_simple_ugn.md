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
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **UGNID** | string | UGN ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **UGN** | [*UGN*](#UGN) | 云联网实例基本信息 |**Yes**|
| **Networks** | array[[*SimpleNetwork*](#SimpleNetwork)] | 加入云联网网络实例基本信息 |**Yes**|
| **BwPackages** | array[[*SimpleBwPackage*](#SimpleBwPackage)] | 云联网下的带宽基本信息 |**Yes**|
| **Routes** | array[[*SimpleRoute*](#SimpleRoute)] | 云联网下的路由基本信息 |**Yes**|
| **Policies** | array[[*Policy*](#Policy)] | 云联网的路由策略基本信息 |No|

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
| **PolicyCount** | int | 关联的路由策略数量 |**Yes**|
| **ApplyNetworksCount** | int | 申请待加入的网络数量 |**Yes**|

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
| **PackageID** | string | 带宽包 ID |**Yes**|
| **UGNID** | string | UGN ID |**Yes**|
| **PayMode** | string | 计费模式 FixedBw:固定带宽｜Peak95:经典95｜Max5:第五峰值｜Traffic:流量计费 |**Yes**|
| **RegionA** | string | 地域A名称 |**Yes**|
| **RegionB** | string | 地域B名称 |**Yes**|
| **BandWidth** | float | 带宽值 |**Yes**|
| **Qos** | string | 服务质量<br />Diamond:钻石｜Platinum:铂金｜Gold:黄金 |**Yes**|
| **Path** | string | 智能路径<br />Delay:最低时延｜IGP:普通线路｜TCO:最低成本 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **Name** | string | 带宽包名称 |No|
| **Remark** | string | 备注 |No|
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

#### Policy

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 作用地域 |No|
| **PolicyId** | string | 路由策略ID |No|
| **Name** | string | 路由策略名称，限定长度255 |No|
| **Direction** | string | 策略方向，限定取值："In"/"Out" |No|
| **Enabled** | boolean | 是否启用 |No|
| **Priority** | int | 策略优先级，范围：[1,255]，数值越小优先级越大，同一方向，策略优先级不可重复 |No|
| **Action** | string | 策略执行动作，限定取值："Permit"/"Deny" |No|
| **RoutePriority** | int | 当执行动作为 "Permit" 时，给匹配中的路由设置路由优先级，范围：[1,255]，数值越小优先级越大 |No|
| **SrcRegions** | array[string] | 路由策略需要匹配的路由的所在地域数组 |No|
| **SrcNetworkTypes** | array[string] | 路由策略需要匹配的路由的网络实例类型数组，限定取值："VPC" / "UWAN-VRouter" |No|
| **SrcNetworks** | array[[*NetworkAndPrefix*](#NetworkAndPrefix)] | 路由策略需要匹配的路由的网络实例类型以及该实例下的网段信息 |No|
| **DstNetworkTypes** | array[string] | 路由策略需要作用的网络实例类型数组，限定取值："VPC" / "UWAN-VRouter" |No|
| **DstNetworks** | array[[*NetworkAndPrefix*](#NetworkAndPrefix)] | 路由策略需要作用的网络实例ID |No|
| **CreateTime** | int | 创建时间 |No|
| **Matched** | boolean | 是否匹配中路由 |No|

#### NetworkAndPrefix

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NetworkId** | string | 网络实例ID |No|
| **Prefixes** | array[string] | 网络实例上报的网段 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSimpleUGN
&ProjectId=org-1jzytw
&UGNID=ugn-1nnk7s9fw238
```

### 响应示例
    
```json
{
  "Action": "DescribeSimpleUGNResponse",
  "BwPackages": [
    {
      "BandWidth": 5,
      "CreateTime": 1781691740,
      "ExpireTime": 1782835200,
      "Name": "test",
      "PackageID": "bw-1rr07fd1f2bl",
      "Path": "IGP",
      "PayMode": "FixedBw",
      "Qos": "Platinum",
      "RegionA": "test03",
      "RegionB": "test05",
      "UGNID": "ugn-1nnk7s9fw238"
    }
  ],
  "Message": "ok",
  "Networks": [
    {
      "CreateTime": 1778478899,
      "Name": "test",
      "NetworkID": "uvnet-1ikw4byoo49w",
      "OrgID": 630018,
      "OrgName": "org-1jzytw",
      "Region": "test05",
      "RegionID": 666006,
      "Type": "VPC"
    }
  ],
  "Policies": [
    {
      "Action": "Deny",
      "CreateTime": 1773214727,
      "Direction": "Out",
      "DstNetworkTypes": [
        "VPC"
      ],
      "DstNetworks": [
        {
          "NetworkId": "uvnet-1jwdo9x2qsui",
          "Prefixes": null
        }
      ],
      "Enabled": false,
      "Matched": false,
      "Name": "22",
      "PolicyId": "policy-lsssp0x5j6",
      "Priority": 100,
      "Region": "test03",
      "RoutePriority": 0,
      "SrcNetworkTypes": [
        "Dedicate-VRouter"
      ],
      "SrcNetworks": [
        {
          "NetworkId": "uplvr-1lykd9bjau1g",
          "Prefixes": null
        }
      ],
      "SrcRegions": [
        "test05"
      ]
    }
  ],
  "RetCode": 0,
  "Routes": [
    {
      "Conflict": false,
      "Deny": false,
      "DstAddr": "10.55.55.0/24",
      "InPolicyId": "",
      "InPolicyName": "",
      "NextHopID": "uvnet-1ikw4byoo49w",
      "NextHopRegion": "test05",
      "NextHopRegionID": 666006,
      "NextHopType": "VPC",
      "OutPolicyId": "",
      "OutPolicyName": "",
      "Priority": 100,
      "Restrict": false
    }
  ],
  "UGN": {
    "ApplyNetworksCount": 0,
    "BwPackageCount": 0,
    "CreateTime": 1772766287,
    "Name": "xxx",
    "NetworkCount": 6,
    "PolicyCount": 0,
    "Remark": "",
    "UGNID": "ugn-1nnk7s9fw238"
  }
}
```





