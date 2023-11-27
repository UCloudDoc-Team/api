# 更新带宽包配置 - UpdateUGNBwPackage

## 简介

更新带宽包配置






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateUGNBwPackage)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateUGNBwPackage`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **PackageID** | string | 带宽包 ID |**Yes**|
| **UGNID** | string | 所绑定的 UGN ID |**Yes**|
| **RegionA** | string |  |**Yes**|
| **RegionABwMax** | int |  |**Yes**|
| **RegionABwMin** | int |  |**Yes**|
| **RegionB** | string |  |**Yes**|
| **RegionBBwMax** | int |  |**Yes**|
| **RegionBBwMin** | int |  |**Yes**|
| **BwBidRate** | float |  |**Yes**|
| **BwULRate** | float |  |**Yes**|
| **PayMode** | string |  |**Yes**|
| **Qos** | string |  |**Yes**|
| **Path** | string |  |**Yes**|
| **Name** | string | 名称 |No|
| **Remark** | string | 备注 |No|
| **ChargeType** | string |  |No|
| **Quantity** | string |  |No|
| **Coupon** | string |  |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateUGNBwPackage
&ProjectId=LAXMcqza
&PackageID=MRMMTEPt
&UGNID=eQvotKqB
&RegionA=ggLmDWAD
&RegionABwMax=4
&RegionABwMin=2
&RegionB=moTANeDU
&RegionBBwMax=6
&RegionBBwMin=1
&BwBidRate=3.15364
&BwULRate=2.36726
&PayMode=okiHsbPL
&Qos=XBtKrlac
&Path=yIHyJBKU
&Name=nxoJMCPf
&Remark=wVZxhZVE
&ChargeType=vhJJUVOT
&Quantity=viLfDviW
&Coupon=MhVBkQHx
```

### 响应示例
    
```json
{
  "Action": "UpdateUGNBwPackageResponse",
  "Message": "vrwgfZwq",
  "RetCode": 0
}
```





