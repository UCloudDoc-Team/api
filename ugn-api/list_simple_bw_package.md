# 获取简洁版带宽包列表 - ListSimpleBwPackage

## 简介

获取当前项目下的带宽包列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListSimpleBwPackage)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListSimpleBwPackage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Offset** | int |  |No|
| **Limit** | int |  |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int |  |**Yes**|
| **Offset** | int |  |**Yes**|
| **Limit** | int |  |**Yes**|
| **BwPackages** | array[[*SimpleBwPackage*](#SimpleBwPackage)] |  |**Yes**|

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
https://api.ucloud.cn/?Action=ListSimpleBwPackage
&ProjectId=ypltSuDF
&Offset=7
&Limit=1
```

### 响应示例
    
```json
{
  "Action": "ListSimpleBwPackageResponse",
  "BwPackages": [
    {
      "ChangePayMode": "TUAmOPJl",
      "ChangeStatus": 1,
      "ChangeTime": 4,
      "CreateTime": 5,
      "ExpireTime": 2,
      "IsCrossBorder": true,
      "Message": "XfyizAyL",
      "Name": "pmUvMYuL",
      "PackageID": "OZCGcLMK",
      "Path": "TCO|IGP|Delay",
      "PayMode": "Free|SolidBw|Peak95|Max5|Traffic",
      "Qos": "金|银|铜",
      "RegionA": "KajgsUSg",
      "RegionABwMax": 8,
      "RegionABwMin": 8,
      "RegionB": "zKmtGPmm",
      "RegionBBwMax": 7,
      "RegionBBwMin": 2,
      "Remark": "nHLwhtiM",
      "UGNID": "EIHoedsh"
    }
  ],
  "Limit": 2,
  "Offset": 7,
  "RetCode": 0,
  "TotalCount": 2
}
```





