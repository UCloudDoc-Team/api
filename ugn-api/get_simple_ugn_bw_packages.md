# 获取云联网内的简洁版带宽包 - GetSimpleUGNBwPackages

## 简介

获取指定云联网内的带宽包






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetSimpleUGNBwPackages)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetSimpleUGNBwPackages`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **UGNID** | string |  |**Yes**|
| **Offset** | int | 偏移量，默认0 |No|
| **Limit** | int | 	<br />分页大小，默认20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BwPackages** | array[[*SimpleBwPackage*](#SimpleBwPackage)] |  |**Yes**|
| **TotalCount** | int |  |**Yes**|
| **Offset** | int |  |**Yes**|
| **Limit** | int |  |**Yes**|

#### 数据模型


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

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetSimpleUGNBwPackages
&ProjectId=WYGwTLkQ
&UGNID=KHzNansp
&Offset=1
&Limit=4
```

### 响应示例
    
```json
{
  "Action": "GetSimpleUGNBwPackagesResponse",
  "BwPackages": [
    {
      "ChangePayMode": "PZOKWlLK",
      "ChangeStatus": 5,
      "ChangeTime": 1,
      "CreateTime": 6,
      "ExpireTime": 6,
      "IsCrossBorder": true,
      "Message": "zdpOXSwS",
      "Name": "KWKYParo",
      "PackageID": "sKSlVKTf",
      "Path": "TCO|IGP|Delay",
      "PayMode": "Free|SolidBw|Peak95|Max5|Traffic",
      "Qos": "金|银|铜",
      "RegionA": "CqjmDate",
      "RegionABwMax": 8,
      "RegionABwMin": 4,
      "RegionB": "yIxKgQxV",
      "RegionBBwMax": 1,
      "RegionBBwMin": 9,
      "Remark": "rpZlMjgK",
      "UGNID": "zuiYmTMN"
    }
  ],
  "Limit": 9,
  "Message": "doKXAKSR",
  "Offset": 2,
  "RetCode": 0,
  "TotalCount": 8
}
```





